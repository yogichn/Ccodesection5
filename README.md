#include <stdio.h>
#include <stdbool.h>
#include <math.h>
bool isprime(int num){
    if(num <= 1){
        return false;
    }
    if(num == 2){
        return true;
    }
    if(num % 2 == 0){
        return false;
    }
    for(int i = 3; i<=sqrt(num); i+=2){
        if(num %i == 0){
            return false;
        }
    }
    return true;
}
bool ispalindrome(int num){
    int org = num;
    int rev = 0;
    while(num != 0){
        int digit = num %10;
        rev = rev*10 +digit;
        num /= 10;
    }
    return org == rev;
}
int gen(int n){
    while(1){
        if(ispalindrome(n) && isprime(n)){
            return n;
        }
        n++;
    }
}
int spp(int (n)){
    int c = n;
    while(1){
        if(ispalindrome(c) && isprime(c)){
            return c;
        }
        c++;
    }
}

int main(){
    int n;
    printf("Enter the value of n: ");
    scanf("%d", &n);
    int result = spp(n);
    printf("%d", result);
    return 0;
}
