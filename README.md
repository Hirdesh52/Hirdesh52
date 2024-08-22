# Basic Quiz Game in Python

# Define a list of questions, options, and the correct answer
quiz_data = [
    {
        "question": "What is the capital of France?",
        "options": ["A) Berlin", "B) Madrid", "C) Paris", "D) Rome"],
        "answer": "C"
    },
    {
        "question": "Which planet is known as the Red Planet?",
        "options": ["A) Earth", "B) Mars", "C) Jupiter", "D) Saturn"],
        "answer": "B"
    },
    {
        "question": "What is the largest ocean on Earth?",
        "options": ["A) Atlantic Ocean", "B) Indian Ocean", "C) Arctic Ocean", "D) Pacific Ocean"],
        "answer": "D"
    }
]

# Function to run the quiz
def run_quiz(quiz_data):
    score = 0  # Initialize the score
    
    # Iterate over each question in the quiz data
    for item in quiz_data:
        print("\n" + item["question"])  # Print the question
        for option in item["options"]:  # Print the options
            print(option)
        
        # Get user input
        user_answer = input("Enter the letter of the correct answer: ").strip().upper()
        
        # Validate user input
        while user_answer not in ["A", "B", "C", "D"]:
            print("Invalid input. Please enter A, B, C, or D.")
            user_answer = input("Enter the letter of the correct answer: ").strip().upper()
        
        # Check if the user's answer is correct
        if user_answer == item["answer"]:
            print("Correct!")
            score += 1  # Increase the score for a correct answer
        else:
            print(f"Incorrect! The correct answer was {item['answer']}.")
    
    # Display the final score
    print(f"\nQuiz completed! Your final score is: {score}/{len(quiz_data)}")

# Run the quiz
run_quiz(quiz_data)
