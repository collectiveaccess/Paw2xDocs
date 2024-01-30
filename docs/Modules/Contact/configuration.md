---
sidebar_position: 2
---

# Contact Form Configuration

## contact.conf

This is documentation for the contact configuration file called contact.conf

### Options

| Option Name   | Explanation  | Example  |
| --- | --- | --- |
| **contact_email**         | Set an array of one or more email addresses to receive the contact email.    | Single Email: `contact_email = {janedoe@collectiveaccess.org}` <br/> Multiple Emails: `contact_email = {janedoe@collectiveaccess.org, johndoe@collectiveaccess.org}`   |
| **check_security**        | This setting checks if there is an arithmetic security question in the form. If set to 0, it will not check. If set to 1, it will check.       | `check_security = 0`     |
| **contact_page_title**    | Set a title for the contact page.   | `contact_page_title = "Contact"`      |
| **contact_form_elements** | An array of elements that will appear in the form. Each key is the name of the form element. For an email address, you can use the `email_address` option to check if a valid email is given. You can set any element as required by passing the `required` option. | ```contact_form_elements = { ``` <br/> ```  itemTitle = { label = _("Item Title")},``` <br/> ```    itemId = { label = _("Item Identifier")}, ``` <br/> ```    itemURL = { label = _("Item URL")}, ``` <br/> ```    email = { label = _("Email address"), email_address = 1, required = 1 }, ``` <br/> ```    name = { label = _("Name"), required = 1}, ``` <br/> ```    message = { label = _("Message"), required = 1} ``` <br/> ```  } ``` |
