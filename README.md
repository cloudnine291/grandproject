# grandproject
def modify_content(content):
    """Modify the content in some way before writing to a new file."""
    return content.upper()  # Example modification: Convert text to uppercase

# Prompt user for a filename
filename = input("Enter the filename to read: ")
new_filename = "modified_" + filename

try:
    # Read the file
    with open(filename, "r") as file:
        content = file.read()
    
    # Modify content
    modified_content = modify_content(content)
    
    # Write to a new file
    with open(new_filename, "w") as new_file:
        new_file.write(modified_content)
    
    print(f"Modified content written to {new_filename}")

except FileNotFoundError:
    print("Error: The file does not exist.")
except IOError:
    print("Error: Unable to read the file.")
