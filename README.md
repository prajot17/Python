# Python
class LoginPage:
    def __init__(self):
        self.users = {}

    def register(self):
        """Register a new user"""
        username = input("Enter a username: ")
        password = input("Enter a password: ")
        confirm_password = input("Confirm your password: ")

        if password == confirm_password:
            self.users[username] = password
            print("User registered successfully!")
        else:
            print("Passwords do not match. Please try again.")

    def login(self):
        """Login to an existing account"""
        username = input("Enter your username: ")
        password = input("Enter your password: ")

        if username in self.users and self.users[username] == password:
            print("Login successful!")
        else:
            print("Invalid username or password. Please try again.")

    def run(self):
        """Run the login page program"""
        while True:
            print("\n1. Login")
            print("2. Register")
            print("3. Exit")
            choice = input("Enter your choice: ")

            if choice == "1":
                self.login()
            elif choice == "2":
                self.register()
            elif choice == "3":
                print("Exiting the program. Goodbye!")
                break
            else:
                print("Invalid choice. Please try again.")


if __name__ == "__main__":
    login_page = LoginPage()
    login_page.run()
