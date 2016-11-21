In order to enable the sending email from xampp you must follow the following step using the following account:
email=trial.rescate1@gmail.com
password=rescate1.trial

1. In C:\xampp\php\php.ini find
1.1. extension=php_openssl.dll and remove the semicolon from the beginning of that line to make SSL working for gmail for localhost.
1.2. [mail function] and change it to:
	SMTP=smtp.gmail.com
	smtp_port=587
	sendmail_from = trial.rescate1@gmail.com
	sendmail_path = "\"C:\xampp\sendmail\sendmail.exe\" -t"
1.3 display_errors=Off

2. Verify if you have sendmail in xampp. If you don't, download it from:
	http://glob.com.au/sendmail/  then you must decompress it and place it in C:\xampp\

3. In C:\xampp\sendmail\sendmail.ini
	3.1. Replace all the existing code in sendmail.ini with following code:
		[sendmail]
		smtp_server=smtp.gmail.com
		smtp_port=587
		error_logfile=error.log
		debug_logfile=debug.log
		auth_username=trial.rescate1@gmail.com
		auth_password=rescate1.trial
		force_sender=trial.rescate1@gmail.com


Reference:
Best answer from,
http://stackoverflow.com/questions/15965376/how-to-configure-xampp-to-send-mail-from-localhost

.