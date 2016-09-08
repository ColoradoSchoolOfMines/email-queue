# Email Queue
***"It works, and it sucks less than mutt."***

Email is awesome. Email clients suck. Email Queue allows you to handle emails the way you want: one
at a time. Email Queue lets you organize your emails into queues and deal with each queue
individually. Only the first item in the queue matters and only the first item in the queue is
shown.

## Requirements
Email Queue will:
- Allow you to organize your emails into queues you define and deal with each queue individually.
- Show you the top item in a selected queue.
- Allow you to switch queues.
- Allow you to have save multiple draft messages at once
- Allow you to access drafts easily
- Let you perform the following actions on the top item in the queue:
    - Delete it
    - Delete it permanently
    - Archive it
    - Move it to another queue
    - Reply to it
    - Delay it (to return to your queue at a later time)
    - Move it back in the queue by x places
    - Move it to the back of the queue
    - Print it?
- Let you do the following to a queue:
    - Flush it
    - Delete the queue itself
    - Archive all inside
    - Move all items in queue to another queue
- Allow you to use multiple accounts
- Automatically send/retrieve emails
- Allow you to manually send/retrieve emails
- Allow you to go into offline mode
- When a new email is retrieved, you will be notified of the new email. You can:
    - Place it in the front of a queue
    - Place it in the back of a queue
    - Place it in a given position in a queue
- Allow you to see the following information on the top email in the current queue:
    - Who it's from
    - Who it's to
    - Date Sent
    - Subject
    - Encryption (or lack thereof)
    - Show the email source
- Be extensible. Very extensible. Build an API for everything.
- Have the following features when writing an email:
    - Allow for plain text
    - Allow for Markdown/LaTeX/HTML/Whatever format to be used.
    - The user will have an option to convert the Markdown/LaTeX/Whatever to HTML
    - The user will have an option to send it as-is (i.e. let the recipient's client decode the
      Markdown)
    - The user will have an option to send it as an attachment (possibly interpreted by something
      like `pdflatex`)
    - Most of this functionality should be plugin-based
- Have a unified inbox for all accounts

## Plugin Ideas
- A plugin that learn to automatically organise your email into your queues? (Maybe this is core to
  server?)
- A HTML email viewer (maybe something like w3m or another [configured] HTML viewer) to view HTML
  emails.
- The ability to send any file as your email. For example, if it's a PDF, then it will be sent as an
  attachment to the recipient, but to you, it will literally be the contents of the email.
- Pull contact information from X where X is any contact management service/application
- Spellcheck

## Implementation
Email Queue will have two components: the client and the server.

### The Client
The client can be anything, we will start with a CLI client. The client will display the emails to
the user and pull the data from the server.

#### User Experience
- Any time that the user interacts with a queue, the current queue will be default.

### The Server
The server will basically be an IMAP wrapper which will keep track of queues and do all of the
intelligent stuff like automagically placing emails into the proper queues.

### APIs
#### Client Only APIs
- APIs for composing emails (autocomplete, syntax highlighting, line wrapping, etc.)
- APIs for email viewer (to view PDF only emails, HTML emails, etc.)

#### APIs that should exist in both Client and Server
- APIs for contacts (contact autocomplete, group email blast list storage, placing certain emails in
  a queue according to the sender)
- APIs for handling incoming messages (HTML email deletion script, this could be where a AI could be
  implemented)
- APIs for conversions of plain text to HTML/PDF/whatever to use as send medium (client or server or
  both or neither or whatever the heck the user wants?)
