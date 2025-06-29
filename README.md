# email-spam-detection

### Purpose:
Counts how many times each word from a provided list appears in a given file (case-insensitive).

### How it works:

Initializes a dictionary with each word (in lowercase) from the provided list, setting the count to 0.
Tries to open the file. If the file doesn’t exist, prints an error and returns None.
Reads the file line by line, converts each line to lowercase, and splits it into words.
Increments the count in the dictionary for each occurrence of the target words.
Returns the dictionary of word counts.

### Example usage:

Counts occurrences of "lottery", "now", and "free" in "spam_email.txt".
Prints the count for each word found.

### Sample Output:
If "lottery" appears 2 times, "now" 1 time, and "free" 4 times, the output would be:

```
'lottery' appears 2 times.
'now' appears 1 times.
'free' appears 4 times.
```

### Error Handling:
If the file doesn’t exist, it prints an error and returns None.
