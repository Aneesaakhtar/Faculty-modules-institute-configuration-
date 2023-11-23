Aneesa Akhtar S23BSEEN1E02012
class Faculty:
    def __init__(self, name, designation):
        self.name = name
        self.designation = designation

    def display_info(self):
        print(f"Name: {self.name}, Designation: {self.designation}")

class Department:
    def __init__(self, name):
        self.name = name
        self.faculties = []

    def add_faculty(self, faculty):
        self.faculties.append(faculty)

    def display_faculties(self):
        print(f"Faculties in {self.name} Department:")
        for faculty in self.faculties:
            faculty.display_info()

class Course:
    def __init__(self, code, name):
        self.code = code
        self.name = name
        self.faculty_in_charge = None

    def assign_faculty(self, faculty):
        self.faculty_in_charge = faculty

    def display_info(self):
        print(f"Course Code: {self.code}, Course Name: {self.name}")
        if self.faculty_in_charge:
            print(f"Faculty in Charge: {self.faculty_in_charge.name}")

# Example Usage
if __name__ == "__main__":
    faculty1 = Faculty("Aqsa", "Professor")
    faculty2 = Faculty("Anissa", "Assistant Professor")

    department = Department("Computer Science")
    department.add_faculty(faculty1)
    department.add_faculty(faculty2)

    course1 = Course("CS101", "Introduction to Computer Science")
    course2 = Course("CS202", "Data Structures")

    course1.assign_faculty(faculty1)
    course2.assign_faculty(faculty2)

    print("Department and Faculty Information:")
    department.display_faculties()

    print("\nCourse Information:")
    course1.display_info()
    course2.display_info()
