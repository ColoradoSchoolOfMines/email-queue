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
- Let you perform the following actions on the top item in the queue:
    - Delete it
    - Delete it permanently
    - Archive it
    - Move it to another queue
    - Reply to it
    - Delay it (to return to your queue at a later time)
    - Move it back in the queue by x places
    - Move it to the back of the queue
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

## Ideas
Email Queue will:
- Learn to automatically organise your email into your queues.
- Use w3m (or other configured HTML viewer) to view HTML emails.
- The ability to send any file as your email. For example, if it's a PDF, then it will be sent as an
  attachment to the recipient, but to you, it will literally be the contents of the email.
- Have a unified inbox for all email accounts? (Plugin)

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
