***# Final Answer:***

When a user composes an email in an email client like Outlook, the client submits the message to the SMTP server, typically Postfix, over port 587 using authenticated SMTP. Postfix validates the sender, applies security and spam policies, and places the message into its queue. It then performs a DNS MX lookup to identify the recipient domain's mail server and establishes an SMTP connection to deliver the email. The recipient's SMTP server accepts the message after performing its own validation and passes it to the Mail Delivery Agent, such as Dovecot, which stores it in the user's mailbox, usually in Maildir format. When the recipient opens their email client, it connects to Dovecot using IMAP or POP3 to retrieve or synchronize the messages.





***# Problem:***

Suppose we have a company with 10,000 employees. Every employee needs to send and receive emails securely. If every computer tried to communicate directly with every other computer, there would be no centralized storage, no authentication, no spam filtering, and no reliable delivery. That's why we use a mail server. It acts as a centralized system that accepts, routes, stores, and delivers emails.





***# Components:***

*User (Alice)*

*↓*

*Mail Client / MUA (Outlook, Gmail)*

*↓*

*SMTP Server which is Postfix*

*↓*

*DNS (MX Record)*

*↓*

*Internet*

*↓*

*Receiving SMTP Server*

*↓*

*Mail Delivery / MDA (Dovecot)*

*↓*

*Mailbox*

*↓*

*User*





***# Working / Actual Flow:***

1. Suppose Alice works in our company and wants to send an email to Bob. 



2\. Alice writes the email in Outlook. Outlook is only a **Mail User Agent(MUA)**. It cannot deliver emails itself, so it submits the email to our SMTP server, which is **Postfix / Mail Transfer Agent(MTA)**.



3\. Postfix first **authenticates** Alice. If authentication fails, the email is rejected. If authentication succeeds, Postfix applies **security checks** like spam policies, antivirus scanning, and relay rules.



4\. After validation, Postfix places the email into its **mail queue**. This queue is very important because if the destination server is temporarily unavailable, the email isn't lost. Postfix retries delivery later.



5\. Now Postfix has to determine where to send the email. It extracts the recipient's domain, for example gmail.com is domain name for alice@gmail.com, and performs a **DNS MX lookup**.



6\. The MX record tells Postfix which mail server is responsible for receiving emails for that domain.



7\. Once the destination server is known, Postfix establishes an **SMTP connection** with the recipient's mail server and transfers the email.



8\. On the receiving side, another SMTP server accepts the email. After its own validation checks, it passes the email to Dovecot.



9\. Dovecot acts as the **Mail Delivery Agent(MDA)**. Its responsibility is to store the email inside the recipient's mailbox and allows users to access them through IMAP or POP3.



10\. Later, when Bob opens Outlook/**MUA** or his mobile email application, the client doesn't communicate with Postfix. Instead, it connects to Dovecot using IMAP or POP3 to read the stored emails.





***# Summary:***

| ----------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |

| Question                                  | Expected Answer                                                                                                                     |

| ----------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |

| What is Postfix?                          | SMTP server / Mail Transfer Agent (MTA) that receives, routes, queues, and sends emails.                                            |

| What is Dovecot?                          | Mail Delivery Agent (MDA) and IMAP/POP3 server that stores mail and allows users to access it.                                      |

| Why do we need Dovecot if Postfix exists? | Postfix transports mail; Dovecot stores mail and serves it to users. They have different responsibilities.                          |

| Why is a queue needed?                    | To retry delivery when the destination server is temporarily unavailable instead of losing emails.                                  |

| What is an MX record?                     | A DNS record that specifies which mail server accepts emails for a domain.                                                          |

| Why are SPF, DKIM, and DMARC used?        | To verify sender identity, protect message integrity, and reduce email spoofing and phishing.                                       |

| Why is IMAP preferred over POP3 today?    | IMAP keeps emails on the server and synchronizes them across multiple devices, whereas POP3 primarily downloads mail to one device. |

| ----------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |





***# Why SMTP?***

SMTP is a push protocol*(only used to send mail from client to server)*. It is designed to transfer emails between clients and servers or between mail servers.



***# POP3:***

Downloads email and removes copy of mail from server. Best for Single device.



***# Why IMAP over POP3?***

Because users need to retrieve and synchronize emails across devices. IMAP Keeps copy on server and Synchronization (Supports Laptop, Phone, Tablet All synchronized.)



***# Why Queue?***

To guarantee reliable delivery. If the recipient's server is temporarily unavailable, Postfix stores the email in the queue and retries later instead of discarding it.

