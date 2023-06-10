# Password-Manager

pw = input("What is the main Password: ")
passwords_dict = {}

def view():
    with open("passwords.txt", 'r') as f:
        for line in f.readlines():
            d = line.rstrip()
            u, p = d.split("|")
            passwords_dict[u] = p
        print(passwords_dict)

def add():
    name = input("Account name: ")
    pwd = input("Password: ")
    with open("passwords.txt", 'a') as f:
        f.write(name + "|" + pwd + "\n")

while True:
    m = input("Would you like to add a new password or view existing ones (view, add)? ").lower()
    if m == "q":
        break
    if m == "view":
        view()
    elif m == "add":
        add()
    else:
        print("Invalid")
