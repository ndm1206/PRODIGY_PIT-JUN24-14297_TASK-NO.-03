
# PRODIGY_PIT-JUN24-01374_TASKNO.03
# Cyber Security Internship
import re

def check_password_complexity(password):
    # Define criteria for password strength
    length_criteria = len(password) >= 8
    uppercase_criteria = any(char.isupper() for char in password)
    lowercase_criteria = any(char.islower() for char in password)
    digit_criteria = any(char.isdigit() for char in password)
    special_char_criteria = bool(re.match(r'[!@#$%^&*(),.?":{}|<>]', password))

    # Calculate overall strength score
    strength_score = sum([length_criteria, uppercase_criteria, lowercase_criteria, digit_criteria, special_char_criteria])

    # Define feedback messages based on strength score
    if strength_score == 5:
        feedback = "Strong password! 👍"
    elif strength_score >= 3:
        feedback = "Moderate password. Consider adding more complexity. 🔒"
    else:
        feedback = "Weak password. Please choose a stronger password. ⚠️"

    return feedback

# Example usage:
password = input("Enter your password: ")
print(check_password_complexity(password))
