## Finding unique characters in text file and  writing them to the output file

```
# Open the input and output files using context managers
with open('read_text_filename.txt', 'r') as readfile, open('write_text_filename.txt', 'w') as writefile:
    # Read all lines from the input file and store them in the 'lines' list
    lines = readfile.readlines()

    # Create an empty list to store characters
    characters = []

    # Loop through each line in the input file
    for line in lines:
        # Split each line into words and characters
        for word in line.split():
            for char in word:
                # Append each character to the 'characters' list
                characters.append(char)

    # Finding unique characters and writing them to the output file
    # Method 1:
    unique_characters1 = sorted(set(characters))
    # Write unique characters to the output file, one character per line
    for char in unique_characters1:
        writefile.write(char + '\n')

    # Method 2:
    unique_characters2 = {}

    # Loop through each character in the 'characters' list
    for char in characters:
        # Use a dictionary to track unique characters and set initial count to 0
        unique_characters2[char] = 0

    # Write unique characters to the output file, one character per line
    for char in unique_characters2:
        writefile.write(char + '\n')
```
