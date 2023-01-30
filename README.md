# TypoSquat-Domain-Comparison
Comparison of the current free tools available to detect potential typos squatting domains and a feature/algorithm overview. 

As part of ongoing improvements i've been focused on typo-squatting domains to help aid potential phishing attacks/brand impersonation. Circl have released a new Typo-Squatting detection tool (https://typosquatting-finder.circl.lu/) which also handily features an API and MISP feed. This activity stemmed from domains being missed from both paid and free solutions. 

For comparison we have identified that DNSTwist detected 14 domains and Circl detected 9592 domains using an example domain. The performance of these tools ultimately stems from the breadth of algorithms used, therefore we have compared and contrasted a number of popular Open Source options, with the results below. With the backing of Circl.lu, typosquatting finder appears the most adept at providing a dataset for respective CoAs. I have raised the feature gaps you see below with Circl for resolution to further assist in detect the acquisition of domain infrastructure (T1583.001).


|          **Algorithms**         	|                                                                                                              **Description**                                                                                                              	| **Circl** 	| **URLInsane** 	| **URLCrazy** 	| **DNSTwist** 	|
|:-------------------------------:	|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:	|:---------:	|:-------------:	|:------------:	|:------------:	|
|           Missing Dot           	|                                                                                      These typos are created by deleting a dot from the domain name.                                                                                      	|     X     	|       X       	|       X      	|       X      	|
|          Missing Dashes         	|                                                                                     Missing Dashes is created by stripping all dashes from the domain                                                                                     	|     X     	|       X       	|              	|              	|
|           Strip Dashes          	|                                                                                      These typos are created by deleting a dash from the domain name.                                                                                     	|     X     	|       X       	|       X      	|              	|
|        Character Omission       	|                                                                         These typos are created by leaving out a letter of the domain name, one letter at a time.                                                                         	|     X     	|       X       	|       X      	|       X      	|
|          Character Swap         	|                                                                           These typos are created by swapping the order of adjacent letters in the domain name.                                                                           	|     X     	|       X       	|       X      	|              	|
| Adjacent Character Substitution 	|                                                                          These typos are created by changing the order of letters in the each part of the domain.                                                                         	|     X     	|       X       	|       X      	|              	|
|   Adjacent Character Insertion  	|                                                                These typos are created by inserting letters to the immediate left and right on the keyboard of each letter.                                                               	|     X     	|       X       	|       X      	|       X      	|
|            Homoglyphs           	|  These typos are created by replacing characters to another character that look similar but are different. An example is that the lower case l looks similar to the numeral one, e.g. l vs 1. For example, google.com becomes goog1e.com. 	|     X     	|       X       	|       X      	|       P      	|
|        Singular Pluralise       	|                                                                                 These typos are created by making a singular domain plural and vice versa.                                                                                	|     X     	|       X       	|       X      	|              	|
|         Character Repeat        	|                                                                                     These typos are created by repeating a letter of the domain name.                                                                                     	|     X     	|       X       	|       X      	|       X      	|
|   Double Character Replacement  	|                                            These typos are created by replacing identical, consecutive letters of the domain name with letters to the immediate left and right on the keyboard.                                           	|     X     	|       X       	|       X      	|              	|
|       Common Misspellings       	|                 These typos are created by changing a word by is misspelling. Over 8000 common misspellings from Wikipedia. For example, www.youtube.com becomes www.youtub.com and www.abseil.com becomes www.absail.com.                	|     X     	|       X       	|       X      	|              	|
|            Homophones           	|                        These typos are created by changing word by an other who sound the same when spoken. Over 450 sets of words that sound the same when spoken. For example, www.base.com becomes www.bass.com.                       	|     X     	|       X       	|       X      	|       P      	|
|          Vowel Swapping         	|                                             These typos are created by swapping vowels within the domain name except for the first letter. For example, www.google.com becomes www.gaagle.com.                                            	|     X     	|       X       	|       X      	|              	|
|           Bitsquatting          	| These typos are created by substituting a character with the set of valid characters that can be made after a single bit flip. For example, facebook.com becomes bacebook.com, dacebook.com, faaebook.com,fabebook.com,facabook.com, etc. 	|     X     	|       X       	|       X      	|       X      	|
|      Wrong Top Level Domain     	|        These typos are created by changing the original top level domain to another. For example, www.trademe.co.nz becomes www.trademe.co.mz and www.google.com becomes www.google.org Uses the 19 most common top level domains.        	|     X     	|       X       	|       X      	|              	|
|    Wrong Second Level Domain    	|                                                                                                                                                                                                                                           	|           	|       X       	|       X      	|              	|
|     Wrong Third Level Domain    	|                                                     These typos are created by placing a dot in the domain name in order to create subdomain. Example: google.com becomes goo.gle.com                                                     	|     X     	|       X       	|              	|              	|
|       Ordinal Number Swap       	|                                                                                                 Numeral Swap numbers, words and vice versa                                                                                                	|           	|       X       	|              	|              	|
|       Cardinal Number Swap      	|                                                                                                 Numeral Swap numbers, words and vice versa                                                                                                	|           	|       X       	|              	|              	|
|           Hyphenation           	|                                                                                                                                                                                                                                           	|           	|               	|              	|       X      	|
|     Combosquatting(Keywords)    	|                                                                                                                                                                                                                                           	|           	|               	|              	|              	|
|             Addition            	|                                                                                      These typos are created by add a characters in the domain name.                                                                                      	|     X     	|               	|              	|              	|
|             AddDash             	|                                                                         These typos are created by adding a dash between the first and last character in a string.                                                                        	|     X     	|               	|              	|              	|
|          ChangeDotDash          	|                                                                                            These typos are created by changing a dot to a dash                                                                                            	|     X     	|               	|              	|              	|
|           Replacement           	|                                     These typos are created by replacing each letter of the domain name with letters to the immediate left and right on the keyboard. (QWERTY, AZERTY, QWERTZ, DVORAK)                                    	|     X     	|               	|              	|              	|
|              AddTld             	|                                                                  These typos are created by adding a tld before the right tld. Example: google.com becomes google.com.it                                                                  	|     X     	|               	|              	|              	|
