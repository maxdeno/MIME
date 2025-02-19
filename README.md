

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







