# Lab 04 - SOP/POS and KMaps

In this lab, you’ve learned how to apply KMaps, Sum Of Products and Products of
sums to simplify digital logic equations. Then, you’ve proven out that they work
using an implemented design on your Basys3 boards.

## Rubric

| Item | Description | Value |
| ---- | ----------- | ----- |
| Summary Answers | Your writings about what you learned in this lab. | 25% |
| Question 1 | Your answers to the question | 25% |
| Question 2 | Your answers to the question | 25% |
| Question 3 | Your answers to the question | 25% |

## Lab Summary

Vivado's verilog is a robust language that can take simple inputs from the brute force truth table logic to either, reduced, concise kmap logic. We implemented circuit design using a naive truth table logic and minimized kmap input (using POS maxterms and SOP minterms), and tested the logic in synthesis and on hardware. The output matched the suggested output of the truth table.

## Lab Questions

### Why are the groups of 1’s (or 0’s) that we select in the KMap able to go across edges?
The edges of a kmap are arbitrary based on our choice of starting point. Most often we start at "00," but as long as only one variable changes from one row or column to the next, then the order doesn't matter. This means that the edges aren't really "there," per se, and the kmap is "tubular," latitudinally and longitudinally

### Why are the names Sum of Products and Products of Sums?
OR is referred to with addition, and AND with multiplication. When you combine the possibilities from the kmap of the terms that combine through AND logic to equal 1 in the output, you are generating a set of products that must, when combined by OR logic, produce this one at the output. This is a Sum of the truth table's Products.
When taking the terms that when combined by OR logic, then combine these by AND logic, you find all the combinations that must be true to produce a 0 at the output. This is a Product of all the Sums of the truth table.
### Open the test.v file – how are we able to check that the signals match using XOR?

Like XOR, this test.v file checks whether the minterms and the maxterms are equal, and if they are not, it produces a 1 to the output. If this output is 1, then an error message is sent saying whether the minterm or the maxterm does not match. 
