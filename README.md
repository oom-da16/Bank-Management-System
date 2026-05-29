*1. Project Overview* 
The Bank Management System is a beginner-level C# Console Application that simulates a real-world 
banking environment. Built entirely on structured programming concepts, it requires no prior knowledge 
of object-oriented programming (OOP), making it ideal as a university mini-project for students learning 
the fundamentals of programming. 

*1.1  What the Application Does* 
• Lets a user create a single bank account with full validation 
• Protects the account with a password-based login system 
• Supports deposits, withdrawals, balance checks, and fund transfers 
• Maintains a live transaction history stored in a List<string> 
• Uses colored console output for a professional, polished look 
• Prevents invalid inputs using loops and conditional logic 

*2. Feature Algorithms* 

*1.  Create New Account*
1. START 
2. Check if accountCreated == true → if yes, show warning and STOP 
3. Prompt for Full Name → validate length >= 2 chars (while loop until valid) 
4. Prompt for Age → validate int between 18 and 100 
5. Prompt for Account Number → validate exactly 10 numeric digits 
6. Prompt for Initial Balance → validate double >= 100.00 
7. Prompt for Password → validate length >= 4 and confirmation matches 
8. Assign all values to global variables 
9. Set accountCreated = true, isLoggedIn = true 
10. Add creation record to transactionHistory list 
11. Display success confirmation 
12. END 


*2.  Deposit Money*
13. START 
14. Call CheckAccountAccess() → if false, STOP 
15. Display current balance 
16. Prompt for deposit amount → validate: is a number AND > 0 AND <= 1,000,000 
17. previousBalance = accountBalance 
18. accountBalance += amount  (arithmetic operator) 
19. Append timestamped entry to transactionHistory 
20. Display updated balance 
21. END 


*3.  Withdraw Money* 
22. START 
23. Call CheckAccountAccess() → if false, STOP 
24. Display current balance 
25. Prompt for withdrawal amount → validate: is a number AND > 0 
26. IF amount > accountBalance → show 'Insufficient Funds' error → STOP 
27. previousBalance = accountBalance
28. accountBalance -= amount  (arithmetic operator) 
29. IF accountBalance < 100 → show low balance warning 
30. Append timestamped entry to transactionHistory 
31. Display updated balance 
32. END 

*4. Transfer Money* 
33. START 
34. Call CheckAccountAccess() → if false, STOP 
35. Prompt for target account number → validate 10 digits AND != own account 
36. Prompt for transfer amount → validate > 0 AND <= accountBalance 
37. Show confirmation summary (from, to, amount) 
38. Prompt 'yes/no' → if not 'yes', cancel and STOP 
39. accountBalance -= amount 
40. Append timestamped 'Transfer Out' entry to transactionHistory 
41. Display transfer receipt 
42. END 

*5.  Login Algorithm* 
43. START 
44. attempts = 0, maxAttempts = 3 
45. WHILE attempts < maxAttempts: 
46.     Prompt for account number and password (masked) 
47.     IF inputAccount == accountNumber AND inputPassword == accountPassword: 
48.         
isLoggedIn = true → show 'Welcome' → RETURN 
49.     ELSE: attempts++ → show remaining attempts 
50. END WHILE (3 failures) 
51. Display 'Account Locked' → call Environment.Exit(0) 
52. END
