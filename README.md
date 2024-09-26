import re
import time
from getpass import getpass

#create a pattern for your desired paasword type
pattern = re.compile(r'^(?=.*[a-z]|[A-Z])(?=.*\d)(?=.*[!@#$%^&*()_+{}|:<>?/~`])[A-Za-z\d!@#$%^&*()_+{}|:<>?/~`]{8,}$')

def check(password):
	if bool(pattern.match(password)) and password[0].isupper():
		return True
	return False

def loggedIn():
	#Login to the wesbiste/App

	time.sleep(5)
	print("Logged in Sucessfully")

def main():
	print("Entered password must:-")
	print(" -Starts with Capital Letter")
	print(" -conatins a digit and special character")
	print(" -at least 8 characters long\n")
	
	password1 = getpass("Enter the Password: ")

	if check(password1)==False:
		print("Enter a vaild password")
	else :
		password2 = getpass("Enter the Password again: ")

		if password1 == password2:
			print("Successfully changed password")
			loggedIn()
		else :
		print("You entered a differnt password")

if __name__ == '__main__':
main()
