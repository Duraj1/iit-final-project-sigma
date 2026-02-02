# iit-final-project-sigma
So sigma
1.	Repetitive task being automated
Normally someone would have to go through each e-mail they get by themselves, decided whether it’s important and what’s the main purpose of the message.

But when new e-mail arrives our system: identifies sender of the e-mail, the topic, the importance, analyzes and summarizes content and then sends a well-structured notification. The system also gives key points of the e-mail content and an explanation of why the e-mail is important.

This saves time, lowers the chance of misunderstanding due to information overload and helps communicate more efficiently.

2.	The workflow logic

- Gmail trigger – starts when an email is received
- HTTP Request – gets the e-mail content, headers and body
- Code in JavaScript -  extracts the name and the subject, replaces polish characters with their equivalents, trims the content to appropriate length for Groq, builds AI Payload for HTTP Request to Groq and returns everything (sender, topic, body, AI Payload)
- HTTP Request – sends AI Payload to Groq, which analyzes the e-mail and returns summary, key points, level of importance and the reason for that
- Code in JavaScript 
- If – checks for error
- HTTP Request – sends a push notification via ntfy

3.	The role of AI

AI reads and interprets content of the e-mail, summarizes it, decides how important it is and why. AI takes the role of an assistant making work more efficient and easier.

4.	System’s execution and testing

Execution: 
The workflow is triggered when an e-mail comes, it pulls the e-mail sender, subject and content. Then AI returns The level of importance and it’s explanation, short summary, key points and finally sends a notification.

Testing:
We tested how the notifications would look like, then we asked more people to send us some test e-mails and made necessary corrections – so the system wouldn’t read only first 300-400 characters and so it would replace polish characters. Then we tested it again and everything was fine.
