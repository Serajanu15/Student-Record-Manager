# Student-Record-Manager
Simple student record manager
# Student Record Manager
# Created by Pallavi Seera

students = []

def add_student():
    name = input("Enter student name: ")
    roll = input("Enter roll number: ")
    branch = input("Enter branch: ")
    students.append({"name": name, "roll": roll, "branch": branch})
    print("✅ Student added successfully.\n")

def view_students():
    if not students:
        print("No student records found.\n")
    else:
        print("\n🎓 All Student Records:")
        for student in students:
            print(f"Name: {student['name']}, Roll: {student['roll']}, Branch: {student['branch']}")
        print()

def delete_student():
    roll = input("Enter roll number to delete: ")
    for student in students:
        if student['roll'] == roll:
            students.remove(student)
            print("🗑️ Student deleted successfully.\n")
            return
    print("❌ Student not found.\n")

def main():
    while True:
        print("=== Student Record Manager ===")
        print("1. Add Student")
        print("2. View Students")
        print("3. Delete Student")
        print("4. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            add_student()
        elif choice == "2":
            view_students()
        elif choice == "3":
            delete_student()
        elif choice == "4":
            print("👋 Exiting program.")
            break
        else:
            print("❌ Invalid choice. Try again.\n")

if __name__ == "__main__":
    main()
