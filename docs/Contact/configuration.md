---
sidebar_position: 2
---

# Contact Form Configuration

## contact.conf

This is documentation for the contact configuration file called contact.conf

### Options

<!-- **contact_email** 
- Set an array of one or more email addresses to receive the contact email. 
- Example:
    -    Single Email:
        `contact_email = {janedoe@collectiveaccess.org}`
    -    Multiple Emails:
        `contact_email = {janedoe@collectiveaccess.org, johndoe@collectiveaccess.org}`

**check_security** 
- This setting checks if there is an arithmetic security question in the form. If set to 0, it will not check. If set to 1, it will check.
- Example: 
    - `check_security = 0`

**contact_page_title** 
- Set a title for the contact page.
- Example: 
    - `contact_page_title = "Contact"`

**contact_form_elements** 
- This is an array of elements that will appear in the form. Each key is what will be the name of the form element. 
- When setting a form element for an email address, you can pass an option called email_address and if set to true, it will check if a valid email address is given.
- You have set any element as required by passing the option required to true.
- Example: 
```
contact_form_elements = {
    itemTitle = { label = _("Item Title")},
    itemId = { label = _("Item Identifier")},
    itemURL = { label = _("Item URL")},
    email = { label = _("Email address"), email_address = 1, required = 1 },
    name = { label = _("Name"), required = 1},
    message = { label = _("Message"), required = 1}
}
``` -->


| Option Name   | Explanation  | Example  |
| --- | --- | --- |
| **contact_email**         | Set an array of one or more email addresses to receive the contact email.    | Single Email: `contact_email = {janedoe@collectiveaccess.org}` <br/> Multiple Emails: `contact_email = {janedoe@collectiveaccess.org, johndoe@collectiveaccess.org}`   |
| **check_security**        | This setting checks if there is an arithmetic security question in the form. If set to 0, it will not check. If set to 1, it will check.       | `check_security = 0`     |
| **contact_page_title**    | Set a title for the contact page.   | `contact_page_title = "Contact"`      |
| **contact_form_elements** | An array of elements that will appear in the form. Each key is the name of the form element. For an email address, you can use the `email_address` option to check if a valid email is given. You can set any element as required by passing the `required` option. | ```contact_form_elements = { ``` <br/> ```  itemTitle = { label = _("Item Title")},``` <br/> ```    itemId = { label = _("Item Identifier")}, ``` <br/> ```    itemURL = { label = _("Item URL")}, ``` <br/> ```    email = { label = _("Email address"), email_address = 1, required = 1 }, ``` <br/> ```    name = { label = _("Name"), required = 1}, ``` <br/> ```    message = { label = _("Message"), required = 1} ``` <br/> ```  } ``` |
