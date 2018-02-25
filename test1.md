# python-learning
def get_user_choice():
    print('-------------------')
    print('Please make a choice: ')
    print('1. Check my list')
    print('2. Add an entry')
    print('3. Modify an entry')
    print('4. Delete an entry')
    print('5. Exit')
    user_input = int(input())
    print('-------------------')
    return user_input


def warning_message():
    print('WARNNING: exiting the program will clear all your data!')
    print('Continue? yes/no')
    if input() == 'yes':
        return True
    return False


def handle_user_request(choice, chechlist):
    if choice == 1:
        if len(chechlist) == 0:
            print('Your list is empty!')
        for i in range(0,len(chechlist)):
            print(i+1, chechlist[i])
        return chechlist
    elif choice == 2:
        new_entry  = input('Type your new to-do here: ')
        checklist.append(new_entry)
        return checklist
    elif choice == 3:
        print('Which do you want to modify?')
        for i in range(0, len(checklist)):
            print(i+1, checklist[i])
        index = int(input()) - 1
        checklist[index] = input('Type your new to-do here: ')
        return checklist
    else:
        print('Which do you want to delete? ')
        for i in range(0, len(checklist)):
            print(i+1, checklist[i])
        index = int(input()) - 1
        del checklist[index]
        return checklist


# Main function
if __name__ == '__main__':
    # Initialize the checklists
    checklist = []

    while True:
        # Get user choice
        choice = get_user_choice()
        # Validate user's input
        if choice < 1 or choice > 5:
            print('Invalid input!')
            continue
        # Handle user's input
        if choice == 5:
            if warning_message():
                print('Goodbye!')
                break
        else:
            checklist = handle_user_request(choice, checklist)

