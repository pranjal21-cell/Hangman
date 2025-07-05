#include<stdio.h>
#include<string.h>
#include<math.h>
#include<time.h>
int main() {
    char word[]="dragon";
    char display[]={'_','_','_','_','_','_'};
    char guess;
    int chances=7;
    int correct=0;
    printf("welcome to the game....lets start!");
while (chances > 0 && correct < 6) {
    printf("\nword");
    for(int i=0;i<6;i++) {
        printf("%c",display[i]);
    }
    printf("\nguess a letter");
    scanf("%c",&guess);
    int match=0;
    for (int i=0;i<6;i++) {
        if (word[i]==guess && display[i]=='_') {
            display[i]=guess;
            correct++;

            match=1;
        }
    }
    if(match==0) {
        chances--;
        printf("wrong guess,%d\n");
    }
    else{
        printf("\ncorrect");
    }
    if(correct==6) {
        printf("\n you won",word);
    }
    else if(chances==0) {
        printf("\nyou lost,restart",word);
        break;
    }
    
}
char play_again;
printf("do you want to play again");
scanf("%c",&play_again);
while(play_again=='y' || play_again=='n');
   return 0;
}
