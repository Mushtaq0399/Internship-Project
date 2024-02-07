# Vedic Multiplier

The proposed Vedic multiplier is based on the Vedic multiplication formulae (Sutras). These Sutras have been traditionally used for the multiplication of two numbers in the decimal number system. 
In this work, we apply the same ideas to the binary number system to make the proposed algorithm compatible with the digital hardware.

## Urdhva Tiryakbhyam sutra

The multiplier is based on an algorithm Urdhva Tiryakbhyam (Vertical & Crosswise) of ancient Indian Vedic Mathematics. 
Urdhva Tiryakbhyam Sutra is a general multiplication formula applicable to all cases of multiplication. It literally means “Vertically and crosswise”. 
It is based on a novel concept through which the generation of all partial products can be done with the concurrent addition of these partial products. 
The parallelism in generation of partial products and their summation is obtained using Urdhava Triyakbhyam explained in figure below. 

![image](https://github.com/Mushtaq0399/Internship-Project/assets/139509924/5fc06903-16e4-4cbd-90c1-317f11fafedb)

To illustrate the multiplication algorithm, let us consider the multiplication of two binary numbers a3a2a1a0 and b3b2b1b0. 
As the result of this multiplication would be more than 4 bits, we express it as... r3r2r1r0. Line diagram for multiplication of two 4-bit numbers is shown in figure below which is nothing but the mapping of the figure 1 (above) in binary system. 
For the simplicity, each bit is represented by a circle. Least significant bit r0 is obtained by multiplying the least significant bits of the multiplicand and the multiplier. 
The process is followed according to the steps shown in figure.

![image](https://github.com/Mushtaq0399/Internship-Project/assets/139509924/2070163d-40a0-4337-9316-160d5f1edfb8)

Firstly, least significant bits are multiplied which gives the least significant bit of the product (vertical). 
Then, the LSB of the multiplicand is multiplied with the next higher bit of the multiplier and added with the product of LSB of multiplier and next higher bit of the multiplicand (crosswise). 
The sum gives second bit of the product and the carry is added in the output of next stage sum obtained by the crosswise and vertical multiplication and addition of three bits of the two numbers from least significant position. 
Next, all the four bits are processed with crosswise multiplication and addition to give the sum and carry. 
The sum is the corresponding bit of the product and the carry is again added to the next stage multiplication and addition of three bits except the LSB. 
The same operation continues until the multiplication of the two MSBs to give the MSB of the product. 
For example, if in some intermediate step, we get 110, then 0 will act as result bit (referred as rn) and 11 as the carry (referred as cn). It should be clearly noted that cn may be a multi-bit number. 

Thus we get the following expressions: 

r0=a0b0; (1) 

c1r1=a1b0+a0b1; (2) 

c2r2=c1+a2b0+a1b1 + a0b2; (3) 

c3r3=c2+a3b0+a2b1 + a1b2 + a0b3; (4) 

c4r4=c3+a3b1+a2b2 + a1b3; (5) 

c5r5=c4+a3b2+a2b3; (6) 

c6r6=c5+a3b3 (7) 

With c6r6r5r4r3r2r1r0 being the final product. Hence this is the general mathematical formula applicable to all cases of multiplication.

![image](https://github.com/Mushtaq0399/Internship-Project/assets/139509924/8910bef4-0325-493d-9140-eb783a4bd698)


Clearly, this is not an efficient algorithm for the multiplication of large numbers as a lot of propagation delay is involved in such cases. To deal with this problem, we now discuss Nikhilam Sutra which presents an efficient method of multiplying two large numbers. 

## Nikhilam Sutra

Nikhilam Sutra literally means “all from 9 and last from 10”. Although it is applicable to all cases of multiplication, it is more efficient when the numbers involved are large. Since it finds out the compliment of the large number from its nearest base to perform the multiplication operation on it, larger is the original number, lesser the complexity of the multiplication. We first illustrate this Sutra by considering the multiplication of two decimal numbers (96 * 93) where the chosen base is 100 which is nearest to and greater than both these two numbers. 

Documentaion for how nikhilam sutra works in attached above.

- Hardware Implementation

  ![image](https://github.com/Mushtaq0399/Internship-Project/assets/139509924/2e1c6ac7-d854-4399-b37d-e73e9dc850bb)

## Conclusion 

The hardware realization of a 4-bit multiplier as shown above. This hardware design is very similar to that of the famous array multiplier where an array of adders is required to arrive at the final product. 
All the partial products are calculated in parallel and the delay associated is mainly the time taken by the carry to propagate through the adders which form the multiplication array.

Tools used: Modelsim 6.5e and Verilog HDL





