# email-notification-code2
#Python code for sending email




import smtplib

from email.message import EmailMessage


def email_alert(subject, body, to):
    msg = EmailMessage()
    msg.set_content(body)
    msg['subject'] = subject
    msg['to'] = to

    user = 'email.alert.projects@gmail.com'
    msg['from'] = user
    password = 'jfsdfkbdsjdflgefakjfdsbogiwfebgjkenw8423984y3h348behbwf' 
#you must create an app password for this to work, this is a filler password

    server = smtplib.SMTP('smtp.gmail.com', 587)
    server.starttls()
    server.login(user, password)
    server.send_message(msg)

    server.quit()


if __name__ == '__main__':
    email_alert("Alert", "Something is down", "email.alert.projects@gmail.com")
