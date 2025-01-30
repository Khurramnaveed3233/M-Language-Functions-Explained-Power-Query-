# M-Language-Functions-Explained-Power-Query-
Power Query’s M Language is a powerful tool for transforming and cleaning data in Excel and Power BI. This repository provides easy-to-understand explanations and real-life examples of commonly used M functions, helping you efficiently work with text, numbers, and data.

📌 Functions Covered:

✅ Text.Replace – Replace specific text in a string

✅ Text.Length – Count the number of characters

✅ Text.Split – Split text into multiple parts

✅ Text.Select – Extract specific characters from text

✅ Number.FromText – Convert text to a number

✅ Text.Lower – Convert text to lowercase

✅ Text.Contains – Check if text contains a word

💡 Perfect for beginners and professionals looking to master Power Query

# 1. Text.Replace – Replace specific text in a string
 
The Text. Replace function in Power Query replaces a specific part of a text string with new text. This function is useful for cleaning, modifying, or standardizing text data in Excel or Power BI.

Syntax: Text.Replace(text as nullable text, old as text, new as text) as nullable text

![tr](https://github.com/user-attachments/assets/2cd06520-05b0-4934-8e11-5e129c392e9d)

Returns the result of replacing all occurrences of text value old in text value text with text value new. This function is case-sensitive.

Example: Replace every occurrence of "the" in a sentence with "a".

![tr2](https://github.com/user-attachments/assets/bf3b41a6-888a-4c7a-9a5f-69b690f518a9)

# 2. Text.Length – Count the number of characters

Returns the number of characters in the text text

![tl](https://github.com/user-attachments/assets/74f6981e-4417-4d70-8155-b027af842086)

Example 1 Find how many characters are in the text "Hello World".

![tl2](https://github.com/user-attachments/assets/cd5600da-cec9-4ea3-9826-01e63203a822)

Output is 11

# 3. Text.Split – Split text into multiple parts

Returns a list of text values resulting from the splitting a text value text based on the specified delimiter, separator.

![ts](https://github.com/user-attachments/assets/1dce78aa-2c60-4a96-9c6c-a7e2d960a480)

Example : Create a list from the "|" delimited text value "Name|Address|PhoneNumber".

![ts2](https://github.com/user-attachments/assets/17016e6c-4f43-4229-948d-637feffc4a6e)

Output

![ts3](https://github.com/user-attachments/assets/e9f307d9-27b1-42f0-933a-b52d033c919a)

# 4. Text.Select – Extract specific characters from text 

Returns a copy of the text value text with all the characters not in selectChars removed.

![tss](https://github.com/user-attachments/assets/7453f86a-8f7d-4ed5-8703-4efd4aa14415)

Example : Select all characters in the range of 'a' to 'z' from the text value.

![tss1](https://github.com/user-attachments/assets/8ad2671d-b1ba-46f6-85df-6220adf24b34)

Output is "abc"

# 5. Number.FromText – Convert text to a number

Returns a number value from the given text value, text.

Syntax is a Number.FromText(text as nullable text, optional culture as nullable text) as nullable number

   - text: The textual representation of a number value. The representation must be in a common number format, such as "15", "3,423.10", or "5.0E-10".
   - culture: An optional culture that controls how text is interpreted (for example, "en-US").

Example:  Get the number value of "4".

![nf](https://github.com/user-attachments/assets/5a01f93d-7fb1-4ea5-91cd-6b029efb3011)

Output is 4

# 6. Text.Lower – Convert text to lowercase

Returns the result of converting all characters in text to lowercase. An optional culture may also be provided (for example, "en-US").

Syntax: Text.Lower(text as nullable text, optional culture as nullable text) as nullable text

Example: Get the lowercase version of "AbCd".

![tll](https://github.com/user-attachments/assets/8a388e99-36a9-4458-b544-9f4b9387dbdd)

Output is "abcd"

# 7. Text.Contains – Check if text contains a word

Detects whether text contains the value substring. Returns true if the value is found. This function doesn't support wildcards or regular expressions.

The optional argument comparer can be used to specify case-insensitive or culture and locale-aware comparisons. The following built-in comparers are available in the formula language:

   - Comparer.Ordinal: Used to perform a case-sensitive ordinal comparison
   - Comparer.OrdinalIgnoreCase: Used to perform a case-insensitive ordinal comparison
   - Comparer.FromCulture: Used to perform a culture-aware comparison

If the first argument is null, this function returns null.

All characters are treated literally. For example, "DR", " DR", "DR ", and " DR " aren't considered equal to each other.

# SQL Server: SUBSTRING aur CHARINDEX Kya Hain?

SUBSTRING kisi bhi string (matlab text) ka ek hissa (part) nikalne ke liye use hota hai.
Syntax: SUBSTRING(string_name, start_position, end_position)

   - start_position: The index where the extraction begins.
   - end_position: The index up to which the extraction continues

Handle Edge Cases:

   - If end_position is greater than or equal to the length of string_name, it returns an empty substring.
   - If end_position equals the length, it also returns an empty substring.
   - If start_position is zero and exceeds the string length, return an empty substring.

![sub](https://github.com/user-attachments/assets/994cfbbc-228d-4f6a-b067-249a963d794e)

By following these steps and understanding the edge cases, you can reliably use the SUBSTRING function in your SQL queries.


CHARINDEX
   
CHARINDEX kisi bhi character ya word ki position dhoondhne ke liye use hota hai.

Syntax:

![c1](https://github.com/user-attachments/assets/f5829f16-9191-43a7-b09a-23ddec34969c)

   - substring: Jis word ya letter ki position chahiye
   - string: Puri line ya text jis men search karna hai

🔹 Example:

![c2](https://github.com/user-attachments/assets/d076603c-93bb-4c6e-a786-b243fb36aaa4)

Output: 9 (Matlab "Ka" ka pehla letter 9th position par hai)

Dono ko sath use karna

Ab hum CHARINDEX se position nikalenge aur SUBSTRING se us word ko extract karenge.

🔹 Example: SELECT SUBSTRING('Hidayat Ka Safar', CHARINDEX('Ka', 'Hidayat Ka Safar'), 2) AS Result;

💡 Output: Ka
Is tarah hum kisi bhi text se dynamically word ya phrase nikal sakte hain! 🚀

# SQL Server: CROSS APPLY aur STRING_SPLIT kya hain?

1. STRING_SPLIT
STRING_SPLIT kisi bhi comma-separated ya space-separated string ko tod kar alag-alag rows me convert karne ke liye use hota hai.

🔹 Example: 

![ss](https://github.com/user-attachments/assets/c4273d68-9325-4ec7-9b87-f6fe219c53ac)

💡 Output:

![ss1](https://github.com/user-attachments/assets/0a2f7314-63f2-4868-91e0-cf3d34f0f95a)

Yani, ek string ko list me tod diya!

2. CROSS APPLY
CROSS APPLY ek table function (STRING_SPLIT jese) ko apply karne ke liye use hota hai. Jab ek column me multiple values (comma-separated) hon, to ye har row ke liye STRING_SPLIT ko apply karta hai.

🔹 Example: Agar ek table ho:

![ca](https://github.com/user-attachments/assets/4c75e1d1-e346-41e4-b0c5-9b7093fdf959)

Ab har fruit ko alag row me dikhane ke liye:

![ca2](https://github.com/user-attachments/assets/7167621b-096e-4f09-ac61-ac5d5e5ee2de)

💡 Output:

![ca3](https://github.com/user-attachments/assets/d0a81347-c49b-42f6-b8f1-073fd066936a)

Samajhne ka Asan Tareeqa

  - STRING_SPLIT sirf ek string ko todta hai.
  - CROSS APPLY ise har row ke liye apply karta hai.
  - Iska use tab hota hai jab ek column me multiple values hon, aur hume har value ko alag row me dikhana ho.
  - Agar database me comma-separated data ho, to ye trick bahut kaam ki hai! 🚀




