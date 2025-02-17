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

    The syntax is: Text.Replace(text as nullable text, old as text, new as text) as nullable text

Returns the result of replacing all occurrences of text value old in text value text with text value new. This function is case-sensitive.

Example: Replace every occurrence of "the" in a sentence with "a".

    The syntax is: Text.Replace("the quick brown fox jumps over the lazy dog", "the", "a")
    
    Output : "a quick brown fox jumps over a lazy dog"


# 2. Text.Length – Count the number of characters

Returns the number of characters in the text text

    The syntax is:  Text.Length(text as nullable text) as nullable number

Example 1 Find how many characters are in the text "Hello World".

    The syntax is: Text.Length("Hello World")

    Output is 11

# 3. Text.Split – Split text into multiple parts

Returns a list of text values resulting from the splitting a text value text based on the specified delimiter, separator.

    The syntax is: Text.Split(text as text, separator as text) as list

Example : Create a list from the "|" delimited text value "Name|Address|PhoneNumber".

    Text.Split("Name|Address|PhoneNumber", "|")

Output

    {
    "Name",
    "Address",
    "PhoneNumber"
    }

# 4. Text.Select – Extract specific characters from text 

Returns a copy of the text value text with all the characters not in selectChars removed.

    The syntax is: Text.Select(text as nullable text, selectChars as any) as nullable text

Example: Select all characters in the range of 'a' to 'z' from the text value.

    Text.Select("a,b;c", {"a".."z"})

    Output is "ABC

# 5. Number.FromText – Convert text to a number

Returns a number value from the given text value, text.

      The syntax is: Number.FromText(text as nullable text, optional culture as nullable text) as nullable number

      text: The textual representation of a number value. The representation must be in a common number format, such as "15", "3,423.10", or "5.0E-10".
      culture: An optional culture that controls how text is interpreted (for example, "en-US").

Example:  Get the number value of "4".

    Number.FromText("4")

    Output is 4

# 6. Text.Lower – Convert text to lowercase

Returns the result of converting all characters in text to lowercase. An optional culture may also be provided (for example, "en-US").

    The syntax is: Text.Lower(text as nullable text, optional culture as nullable text) as nullable text

Example: Get the lowercase version of "AbCd".

    Text.Lower("AbCd")

    Output is "abcd"

# 7. Text.Contains – Check if text contains a word

Detects whether text contains the value substring. Returns true if the value is found. This function doesn't support wildcards or regular expressions.

The optional argument comparer can be used to specify case-insensitive or culture and locale-aware comparisons. The following built-in comparers are available in the formula language:

   - Comparer.Ordinal: Used to perform a case-sensitive ordinal comparison
   - Comparer.OrdinalIgnoreCase: Used to perform a case-insensitive ordinal comparison
   - Comparer.FromCulture: Used to perform a culture-aware comparison

If the first argument is null, this function returns null.

All characters are treated literally. For example, "DR", " DR", "DR ", and " DR " aren't considered equal to each other.

    The syntax is: Text.Contains(text as nullable text, substring as text, optional comparer as nullable function) as nullable logical

Example: Find if the text "Hello World" contains "Hello".

    Text.Contains("Hello World", "Hello")

    Output = true
    
# SQL Server: SUBSTRING aur CHARINDEX Kya Hain?

1. SUBSTRING
SUBSTRING kisi bhi string (matlab text) ka ek hissa (part) nikalne ke liye use hota hai.

Syntax: 

    - SUBSTRING(string, start_position, length)
    
    - string: Jis text se hissa nikalna hai
    - start_position: Kahan se start karna hai
    - length: Kitne characters lene hain
 
Example:SELECT SUBSTRING('Hidayat Ka Safar', 9, 2) AS Result;

    - Output: Ka

2. CHARINDEX
   
CHARINDEX kisi bhi character ya word ki position dhoondhne ke liye use hota hai.

Syntax:

      CHARINDEX(substring, string)

      substring: Jis word ya letter ki position chahiye
      string: Puri line ya text jis men search karna hai

🔹 Example:

      SELECT CHARINDEX('Ka', 'Hidayat Ka Safar') AS Position;

      Output: 9 (Matlab "Ka" ka pehla letter 9th position par hai)

Dono ko sath use Karna

Ab hum CHARINDEX se position nikalenge aur SUBSTRING se us word ko extract karenge.

      Example: SELECT SUBSTRING('Hidayat Ka Safar', CHARINDEX('Ka', 'Hidayat Ka Safar'), 2) AS Result;

      Output: Ka
    
Is tarah hum kisi bhi text se dynamically word ya phrase nikal sakte hain! 🚀

# SQL Server: CROSS APPLY aur STRING_SPLIT kya hain?

1. STRING_SPLIT
STRING_SPLIT kisi bhi comma-separated ya space-separated string ko tod kar alag-alag rows me convert karne ke liye use hota hai.

🔹 Example: 

      SELECT value FROM STRING_SPLIT('Apple,Banana,Orange, ',');
      Output: Apple
              Banana
              Orange
              
Yani, ek string ko list me tod diya!

2. CROSS APPLY
CROSS APPLY ek table function (STRING_SPLIT jese) ko apply karne ke liye use hota hai. Jab ek column me multiple values (comma-separated) hon, to ye har row ke liye STRING_SPLIT ko apply karta hai.

🔹 Example: Agar ek table ho:

![T](https://github.com/user-attachments/assets/6411bbd7-cd7c-4fbe-b901-69b95a285791)

Ab har fruit ko alag row me dikhane ke liye:

    SELECT ID, value AS Fruit FROM MyTable  CROSS APPLY STRING_SPLIT(Fruits, ',');

Output: 

    1	Apple
    1	Banana
    2	Orange
    2	Mango
    
Samajhne ka Asan Tareeqa

  - STRING_SPLIT sirf ek string ko todta hai.
  - CROSS APPLY ise har row ke liye apply karta hai.
  - Iska use tab hota hai jab ek column me multiple values hon, aur hume har value ko alag row me dikhana ho.
  - Agar database me comma-separated data ho, to ye trick bahut kaam ki hai! 🚀

Agar database me comma-separated data ho, to ye trick bahut kaam ki hai! 🚀

# Normalization and Denormalization 

Normalization: A Cleanse Database Through Duplicates and Redundancies

Normalization is a database normalization process aimed at minimizing redundancy and eliminating duplicates. It ensures that the database tables are clean, reducing data duplication and improving data integrity.

   - Removing Redundancy: When a table contains multiple entries for the same information across different records, it indicates unnecessary redundancy. For example, if two customers 
     have the same customer ID due to duplicate entries in the "Customer" table, normalization eliminates this duplication by ensuring each customer ID is unique.

   - Eliminating Duplicates: Duplicates within a single table can cause issues when querying data. By normalizing tables, we remove such duplicates, making it easier to retrieve 
     specific information without redundancy.

   - Maintaining Relationships: Normalization ensures that all relationships between data are accurately represented in the database schema. This helps in maintaining the integrity of 
     data and avoids scenarios where two or more records should be identical but are not.

Denormalization: Rebuilding Cleaned Tables

Denormalization is the inverse process of normalization. Instead of removing redundant entries, denormalization re-expands normalized tables into their original form with additional columns that capture all possible relationships between data in multiple tables.    

   - Recreating Tables: After normalizing a database by splitting it into separate tables, denormalization involves adding new tables or modifying existing ones to include all 
     necessary information from the normalized tables.

   - Maintaining Existing Data: Denormalization ensures that all original data remains intact in its original form, allowing for easy querying of specific details without needing to 
     reprocess entire tables each time a change is made.

   - Flexibility and Organization: By reorganizing data into separate tables, denormalization provides flexibility for future expansions or additions. This approach keeps the database 
     clean and organized, making it easier to manage and extend as needed.

In summary, normalization cleans up databases by removing redundancies and eliminating duplicates, while denormalization brings normalized tables back into their original form, maintaining existing data integrity. Both processes work together toward creating a well-organized and efficient database structure.

Normalization and denormalization are key concepts in database design that help manage redundancy and ensure data integrity. Here's a clearer explanation using tables as an example:

Basic Table Structure:

    Consider a simple "Students" table with columns: ID, Name, Age, Subject, Grade

Normalization Process:

    Objective: Eliminate redundancy by ensuring each field represents a single piece of information.
    Example: Split the "Subject" column into separate tables for each subject area (e.g., Mathematics, Physics).
    This creates normalized sub-tables where each table focuses on one specific aspect of data without duplicating information across columns.

Denormalization Process:

    Objective: Reinsert normalized tables back into their original form.
    Example: Bring these normalized sub-tables back into the "Students" table, possibly by combining IDs from different tables to maintain consistency and accuracy.

Data Integrity and Relationships:

    Ensure that relationships (e.g., between subjects and grades) are maintained across all tables, both in their normalized form and when re-established.
    During denormalization, verify that data flows correctly without introducing errors caused by migration.

Conclusion:

    Normalization helps manage redundancy, while denormalization ensures data integrity and consistency when moving from normalized to original table structures.
    Through these examples, normalization and denormalization become more approachable concepts, demonstrating how they maintain data integrity and structure in database design.
