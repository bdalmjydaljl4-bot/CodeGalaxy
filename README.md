# ==============================================
# Student Grades Project
# By: [Your Name]
# Description: This project calculates total, average, and letter grade for each student,
# and also finds the highest and lowest scorer in each subject.
# المشروع يحسب المجموع، المتوسط، والتقدير لكل طالب
# ويعرض أعلى وأقل طالب لكل مادة
# ==============================================

# List of students with their grades
students = [
    {"name": "Abood", "grades": [80, 90, 75, 85]},
    {"name": "Nova", "grades": [95, 88, 92, 90]},
    {"name": "Saeed", "grades": [70, 60, 80, 75]}
]

# List of subjects (same order as grades)
subjects = ["Math", "Science", "Language", "History"]  # الرياضيات، العلوم، اللغة، التاريخ

# Function to calculate total and average grades
def calculate(grades):
    total = sum(grades)  # sum of grades المجموع
    average = total / len(grades)  # average المتوسط
    return total, average

# Function to determine letter grade
def grade_letter(average):
    if average >= 90:
        return "A"
    elif average >= 80:
        return "B"
    elif average >= 70:
        return "C"
    else:
        return "D"

# Display results for each student
for student in students:
    total, average = calculate(student["grades"])
    letter = grade_letter(average)
    
    print(f"\nStudent: {student['name']}")  # اسم الطالب
    for i in range(len(subjects)):
        print(f"{subjects[i]}: {student['grades'][i]}")  # درجة كل مادة
    print(f"Total: {total}")  # المجموع
    print(f"Average: {average}")  # المتوسط
    print(f"Grade: {letter}")  # التقدير

# Find highest and lowest student for each subject
for i, subject in enumerate(subjects):
    highest_student = max(students, key=lambda s: s["grades"][i])
    lowest_student = min(students, key=lambda s: s["grades"][i])
    print(f"\nSubject: {subject}")  # المادة
    print(f"Highest: {highest_student['name']} with {highest_student['grades'][i]}")  # أعلى طالب
    print(f"Lowest: {lowest_student['name']} with {lowest_student['grades'][i]}")  # أقل طالب
