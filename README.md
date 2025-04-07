def read_and_write_file():
    input_filename = input("Enter the name of the file you want to read: ")
    output_filename = input("Enter the name of the file to save the modified content: ")

    try:
        with open(input_filename, 'r') as infile:
            content = infile.read()
            print(f"Original content from {input_filename}:")
            print(content)

            modified_content = content.upper()

            with open(output_filename, 'w') as outfile:
                outfile.write(modified_content)
            print(f"Modified content has been written to {output_filename}.")

    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' was not found.")
    except IOError:
        print(f"Error: The file '{input_filename}' cannot be read.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")


read_and_write_file()
