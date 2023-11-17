# PyMailJet-Pythonic-Email-Magic-
from email.message import EmailMessage
import ssl
import smtplib
email_sender = 'pythonpypy2023@gmail.com'
email_password = ''#paste your password gendrated my google account
email_receiver = 'abc@gmail.com'
subject = 'hey guys :)'
body = ' This is the code for sending emails using python, Hope it works well'
em=EmailMessage()
em['From']=email_sender
em['To']=email_receiver
em['Subject']=subject
em.set_content(body)
context=ssl.create_default_context()
with smtplib.SMTP_SSL('smtp.gmail.com',465,context=context) as smtp:
    smtp.login(email_sender,email_password)
    smtp.sendmail(email_sender,email_receiver,em.as_string())
print('email sent successfully!!')
