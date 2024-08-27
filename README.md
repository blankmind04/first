# Python line code

import gradebook

def main():
    courses = {}

    while True:
        print("\n Book menu:")
        print("1.add course")
        print("2.add grade")
        print("3.calculate overall grade")
        print("4.view grades")
        print("5.view average grade")
        print("6.quit")

        choice = input("Enter your choice:")

        if choice == '1':
            course_name = input("Enter your course name :")
            gradebook.add_course(courses, course_name)
        elif choice == "2":
            course_name = input("Course course name:")
            grade = float(input("Enter Grade:"))
            gradebook.add_grade(courses, course_name, grade)
            
        elif choice == "3":
            course_name =  input("Enter Course Name:")
            overall_grade = grade_book.calculate_overall_grade(courses, course_name)
            if overall_grade is not None:
                print(f"Overall Grade for {course_name}: {overall_grade:.2f}")
        elif choice == "4":
            course_name = input("Enter Course name:")
            gradebook.view_grades(courses, course_name)
        elif choice == "5":
            course_name = input("Enter Course name :")
            gradebook.view_average_grade(courses, course_name)
        elif choice == "6":
            break
        else:
            print("Invalid Choice. Please try again.")

if __name__ == "__main__":
    main()


# Module code


#grade_book.py
#1
def add_course(courses,course_name):
    courses[course_name]=[]
   
#2
def add_grade(courses,course_name,grade):
    if course_name in courses:
        courses[course_name].append(grade)
    else:
        print("Course not found.")

#3
def calculate_overall_grade(courses,course_name):
    if course_name in courses:
        grades=courses[course_name]
        overall_grade=sum(grades)/len(grades)
        return overall_grade
    else:
        print("Course not found.")
        return None

#4
def view_grades(courses,course_name):
    if course_name in courses:
        grades=courses[course_name]
        print(f"Grades for {course_name}: {grades}")
    else:
        print("Course not found")

#5
def view_average_grade(courses,course_name):
    if course_name in courses:
        overall_grade=calculate_overall_grade(courses,course_name)
        if overall_grade is not None:
            print(f"Average grade for {course_name}: {overall_grade:.2f}")
    else:
        print("Course not found.")

