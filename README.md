

# MIME
A Multipurpose Internet Mail Extension is an email standard that allows email to include texts, audio, video and attachments.
Without MIME, email communication is only limited to texts.

# MIME Format
Headers – Contains metadata (e.g., sender, recipient, subject).<br>
MIME-Version – Specifies MIME usage (always "1.0").<br>
Content-Type – Defines the format (plain text, HTML, images, attachments).<br>
Content-Encoding – Defines how data is encoded (Base64 for images/files).<br>

# Content Types
MIMEText -	Plain text or HTML content<br>
MIMEImage	- Images (JPEG, PNG, etc.)<br>
MIMEAudio	- Audio files<br>
MIMEApplication	- PDFs, Word Docs, ZIP files<br>
MIMEMultipart	- Combines multiple parts(text, images etc)<br>

# Question❓
Your current SMTP mail client only handles sending text messages in the email body. Modify your
client such that it can send emails with both text and images

# Answer 🎯
Using MIME, The smtp_client has been updated to send an image alongside the text message. The new code includes:
- MIMETEXT() module
- MIMEIMAGE() module
The smtp_client code remains the same.





# SMTP Client side


![Image](https://github.com/user-attachments/assets/0c36c146-f75f-4e68-b2d0-720f15b8b2a9)



# Recipient's Email.


![Image](https://github.com/user-attachments/assets/0acf3462-9dcd-4bc1-b894-6020d9cba282)

# SMTP_CLIENT

#🎯 Task
Develop a simple mail client that sends email to any recipient. Your client will need to
connect to a mail server, dialogue with the mail server using the SMTP protocol, and send an email
message to the mail server.

# Factors considered:
1. Mail server: Smtp.gmail.com  used.
2. Authentication: using the app password feature in the google's gmail.<br>
   The app password enables simple mail client to authenticated by the smtp server.<br>
3. Firewall and network settings.
   The smtp port 25 can't be used due to its restrctions.<br>
   check if the network or firewall allows traffic through the smtp ports, i.e port 587, 425.<br>
   use mobile network, vpn or change the firewall rule to allow traffic.<br>

# Action Plan
1. Establish a TCP connection to smtp.gmail.com on port 587.<br>
2. Perform SMTP handshake(EHLO, MAIL FROM, RCPT TO).<br>
3. Upgrade the connection to Transport Layer Security, and encrpyt the connection in secure socket layer.  Makes the coonection more secure.<br>
4. Authenticate the SMTP Client using encoded Base64 credentials.<br>
5. Send the message.<br>
6. close the connection and quit the session.<br>

# Operation
The smtp client connects with the smtp server, performing authentication to enhance the connection. Once the connection is established, the server and client perform a handshake i.e EHLO, MAIL TO, RCPT TO commands. After the handshaking process is completed, the client sends the email body to the server and the server forwards it to the recipient's email address.

# Status code:
2xx(Success)<br>
220 - server is ready for coonection.<br>
250 - Action initiated by the smtp client has been accepted by the server.<br>
235 - Authentication successful.<br>
221 - server closing the connection.<br>

3xx(Immediate response)<br>
334 - server requesting for authentication details.<br>
335 - server ready to receive email.<br>

4xx(Temporary Failure)<br>
421 -	Service unavailable (server shutting down)<br>
450 - Mailbox unavailable (e.g., user’s inbox is full)<br>
451 -	Server error (e.g., temporary server issue)<br>
452 -	Too many emails sent (server has rate limits)<br>

5xx(Permanent Failure)<br>
500 - Syntax error (invalid command)<br>
501 -	Invalid email address<br>
503 -	Incorrect command sequence (e.g., sending MAIL FROM before HELO)<br>
550 -	Email not delivered (recipient address doesn't exist)<br>
554 -	Message rejected (e.g., spam detected)<br>


SMTP backend status:
![Image](https://github.com/user-attachments/assets/49e932bf-f6db-4511-8037-03cba0d21c89)

Recipient email inbox:
![Image](https://github.com/user-attachments/assets/5980c99e-683c-45dc-8b90-e0365e2e4549)





