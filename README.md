#include <stdio.h>
#include <string.h>
#include <ctype.h>

#define MAX_QUESTION 256
#define MAX_ANSWER 128

#define TOTAL_QUESTIONS 5

typedef struct
{
  char question[MAX_QUESTION];
  char answerA[MAX_ANSWER];
  char answerB[MAX_ANSWER];
  char answerC[MAX_ANSWER];
  char answerD[MAX_ANSWER];
  char correct_answer;
} quiz_question;

int main(void)
{
   printf("  Welcome to Rafi Geovazi Movie Quiz\n\n");
  quiz_question quiz[TOTAL_QUESTIONS];
  
  strcpy(quiz[0].question, "Who is Ryan Gosling?");
  strcpy(quiz[0].answerA, "Actor");
  strcpy(quiz[0].answerB, "Rafi Geovazi's second personality");
  strcpy(quiz[0].answerC, "NPC's");
  strcpy(quiz[0].answerD, "No one");
  quiz[0].correct_answer = 'B';
  
  strcpy(quiz[1].question, "Who played Mark Zuckerberg in the social network?");
  strcpy(quiz[1].answerA, "Jesse Eisenberg");
  strcpy(quiz[1].answerB, "Clint Eastwood");
  strcpy(quiz[1].answerC, "Bill Murray");
  strcpy(quiz[1].answerD, "Jonah Hill");
  quiz[1].correct_answer = 'A';
  
  strcpy(quiz[2].question, "What's the name of the skyscraper in Die Hard?");
  strcpy(quiz[2].answerA, "Burj Khalifa");
  strcpy(quiz[2].answerB, "Basko Padang");
  strcpy(quiz[2].answerC, "Plaza Andalas Padang");
  strcpy(quiz[2].answerD, "Nakatomi Plaza");
  quiz[2].correct_answer = 'D';
  
  strcpy(quiz[3].question, "The code in The Matrix comes from what food recipes?");
  strcpy(quiz[3].answerA, "Croissant");
  strcpy(quiz[3].answerB, "Cheese Burger");
  strcpy(quiz[3].answerC, "Sushi");
  strcpy(quiz[3].answerD, "Nasi Ampera");
  quiz[3].correct_answer = 'C';
  
  strcpy(quiz[4].question, "Where were The Lord Of The Rings movies filmed?");
  strcpy(quiz[4].answerA, "Indonesia");
  strcpy(quiz[4].answerB, "New Zealand");
  strcpy(quiz[4].answerC, "USA");
  strcpy(quiz[4].answerD, "North Korea");
  quiz[4].correct_answer = 'B';

  double total_correct = 0;
  
  char answer;
  
  for (int i = 0; i < TOTAL_QUESTIONS; i++)
  {
    printf("Question %d: %s\n\n", (i+1), quiz[i].question);
    
    printf("A) %s\n", quiz[i].answerA);
    printf("B) %s\n", quiz[i].answerB);
    printf("C) %s\n", quiz[i].answerC);
    printf("D) %s\n", quiz[i].answerD);

    printf("\nEnter Answer (A,B,C or D): ");
    
    scanf(" %c", &answer);
    
    if (toupper(answer) == quiz[i].correct_answer)
    {
      total_correct++;
      printf("\n\nCorrect Answer!");
    }
    else
    {
      printf("\n\nIncorrect Answer!");
      printf("\n\nThe correct answer was %c.", quiz[i].correct_answer);
    }
    
    printf("\n\n\n");
  }

  printf("%d/%d questions answered correctly",
         (int) total_correct, 
         TOTAL_QUESTIONS);

  printf(" (%.2f%%)\n\n", (total_correct / TOTAL_QUESTIONS) * 100);

  return 0;
}
