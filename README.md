# hw1a

#include <stdio.h>

int getbits(int regval, int lft_idx, int rgt_idx)

{

//Assign rgt_idx to variable p
int p = rgt_idx;

//count number of bits to extract i.e lft_idx - rgt_idx + 1 and assign to k
int k = lft_idx - rgt_idx + 1;

//Right shift by p bits like for example 0x12345678, If we right shift by 4 bits we will get 0x1234567
// Left shift 1 by K , for us k will be 8 (11 - 4 + 1 = 8) , So 1 <<8 then substract 1 it will result in 0000011
// Then Multiply both of them 0000011 & 0x1234567 , we will get 0x67
return (((1 << k) - 1) & (regval >> (p)));

}

int main()

{

printf("0x%x", getbits(0x12345678, 11, 4));

return 0;

}
