# Practice: Request a session form

Page: `services.html`. Element: `form.session-form`. Checked 3 Oct 2026 in Chrome 148.

Standards checked: WCAG 2.2 Success Criteria 1.3.1, 2.4.3, 2.4.7, 3.3.1, 3.3.2, and 4.1.2. HTML `required` and `type="email"` messages were read from the page.

## Checklist

### Labels

Standard: 1.3.1, 3.3.2.

Observed: `label for` matches the field `id` for `name`, `email`, and `interest`. Label text: "Name (required)", "Email (required)", "Area of interest (required)".

Impact: Each control has a visible label tied to it.

Priority: none.

Retest: reload `services.html` and check each `for` against each `id`.

### Instructions

Standard: 3.3.2.

Observed: Each label ends with "(required)". On load, `#email-error` is on screen: "Enter an email we can reply to, not only a colored border." `display` is `block`. Name and Area of interest have no other instruction.

Impact: The email format appears as that error under the loaded value `not-an-email`.

Priority: low.

Retest: reload and read the text under each label before typing.

### Required state

Standard: 4.1.2. HTML `required`.

Observed: Name, Email, and Area of interest have `required`. In the accessibility tree, Name and Email expose required. Email also exposes invalid. Area of interest exposes invalid. The source has no `aria-invalid` on Area of interest. The first option is "Choose one" with `value=""`.

Impact: Empty Name is required and not marked invalid until submit. Area of interest is marked invalid on load with no error text.

Priority: medium.

Retest: reload, open the accessibility tree, and record required and invalid on all three fields.

### Errors

Standard: 3.3.1, 4.1.2.

Observed: Email loads with `aria-invalid="true"`, `aria-describedby="email-error"`, and `.field.is-invalid`. The tree name is "Email (required)". The description is the `#email-error` text. The border color is `rgb(122, 69, 0)`.

After the value was changed to `name@example.com`, `validity.valid` was true and the browser validation message was empty. `aria-invalid` stayed `true`, `.is-invalid` stayed, the error stayed `display: block`, and the tree still showed invalid.

Submit with the fields as loaded focused Name. Message: "Please fill out this field."

Name filled, Email left as `not-an-email`, Area of interest left on "Choose one": focus moved to Email. Message: "Please include an '@' in the email address. 'not-an-email' is missing an '@'."

Email set to `name@example.com`, Area of interest left on "Choose one": focus moved to Area of interest. Message: "Please select an item in the list." That message is not an element in the page. Name has no error element either.

Impact: A corrected email stays invalid and the error text stays. Name and Area of interest errors are only in the browser message.

Priority: high for the email state. Medium for Name and Area of interest.

Retest: set Email to `name@example.com` and read `aria-invalid`, the error text, and the invalid state. Submit once with Name empty and once with Area of interest on "Choose one". Record the message and whether it is in the page.

### Submit button

Standard: 4.1.2.

Observed: One `button type="submit"`. Accessible name: "Submit request".

With Name filled, Email `name@example.com`, and Area of interest "Online technique", submit sent `POST /services.html`. The response title was "Error response". The text was "Error code: 501" and "Unsupported method ('POST')." The URL was `services.html#`. The form source has no confirmation text.

Impact: A completed submit left the form. The static file server returned 501 for POST.

Priority: low.

Retest: submit the same three values and record the URL, title, and whether the form is still on screen.

### Keyboard path

Standard: 2.4.3, 2.4.7.

Observed: In the form, the focusable order is Name, Email, Area of interest, Submit request. None of them has `tabindex`. `base.css` sets `:focus-visible` to 3px solid, offset 3px, color `#9b1c1c`. A Tab press in this session did not move `document.activeElement`. The ring was not recorded on a key press.

Impact: The source order matches the fields on screen. The ring was not observed from a key press.

Priority: low.

Retest: click the address bar, Tab to Name, and record each stop through Submit request, including outline width, style, color, and offset.

### Accessible names

Standard: 4.1.2.

Observed in the accessibility tree:

- textbox "Name (required)", required, invalid false, no description
- textbox "Email (required)", required, invalid true, description from `#email-error`, `describedby` `email-error`
- combobox "Area of interest (required)", invalid true, no description
- button "Submit request"

Impact: Names come from the labels. Only Email has a description. That description stayed after the value was valid.

Priority: high. Same item as the email error.

Retest: reload, then repeat after a valid email, and record name, required, invalid, and description for each control.

## Remediation plan

1. When Email is valid, remove `aria-invalid="true"` and `.is-invalid`, and hide `#email-error`. Retest by replacing `not-an-email` with `name@example.com` and reading the invalid state and the error text.

2. Add error text in the page for Name and for Area of interest, each tied with `aria-describedby`. Show the Name text when that field is empty on submit. Show the Area of interest text when it is still "Choose one" on submit. Retest both submits and record the message in the page and the focused field.
