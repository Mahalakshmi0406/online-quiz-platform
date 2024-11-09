import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class Question {
    private String questionText;
    private String[] options;
    private int correctAnswerIndex;

    public Question(String questionText, String[] options, int correctAnswerIndex) {
        this.questionText = questionText;
        this.options = options;
        this.correctAnswerIndex = correctAnswerIndex;
    }

    public String getQuestionText() {
        return questionText;
    }

    public String[] getOptions() {
        return options;
    }

    public boolean isCorrect(int answerIndex) {
        return answerIndex == correctAnswerIndex;
    }

    @Override
    public String toString() {
        StringBuilder sb = new StringBuilder();
        sb.append(questionText).append("\n");
        for (int i = 0; i < options.length; i++) {
            sb.append(i + 1).append(". ").append(options[i]).append("\n");
        }
        return sb.toString();
    }
}

class Quiz {
    private List<Question> questions;
    private int score;
    private int currentQuestionIndex;

    public Quiz(List<Question> questions) {
        this.questions = questions;
        this.score = 0;
        this.currentQuestionIndex = 0;
    }

    public void startQuiz() {
        Scanner scanner = new Scanner(System.in);
        while (currentQuestionIndex < questions.size()) {
            Question currentQuestion = questions.get(currentQuestionIndex);
            System.out.println(currentQuestion);
            System.out.print("Your answer (1-" + currentQuestion.getOptions().length + "): ");
            int answer = scanner.nextInt();

            if (currentQuestion.isCorrect(answer - 1)) {
                score++;
                System.out.println("Correct!\n");
            } else {
                System.out.println("Incorrect. The correct answer was " + (currentQuestionIndex + 1) + ".\n");
            }
            currentQuestionIndex++;
        }
        System.out.println("Quiz finished! Your score: " + score + " out of " + questions.size());
    }
}

public class Main {
    public static void main(String[] args) {
        // Create some sample questions
        List<Question> questionList = new ArrayList<>();
        
        questionList.add(new Question(
            "What is the capital of France?", 
            new String[] {"Berlin", "Madrid", "Paris", "Rome"}, 
            2 // Index of correct answer (Paris)
        ));
        
        questionList.add(new Question(
            "Which of the following is a Java programming language feature?",
            new String[] {"Pointer Arithmetic", "Automatic Garbage Collection", "Assembly Code", "Direct Memory Access"},
            1 // Index of correct answer (Automatic Garbage Collection)
        ));
        
        questionList.add(new Question(
            "Which of the following is the largest planet in our solar system?",
            new String[] {"Earth", "Mars", "Jupiter", "Saturn"},
            2 // Index of correct answer (Jupiter)
        ));

        // Create the quiz with the list of questions
        Quiz quiz = new Quiz(questionList);

        // Start the quiz
        quiz.startQuiz();
    }
}
