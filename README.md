# CSC_302_ICA3

import csv
from google.colab import drive

# Mount Google Drive
drive.mount('/content/drive')

def read_and_split_csv(file_path, max_lines=1000):
    """
    Reads the first `max_lines` from a CSV file and splits each line by commas.

    :param file_path: Path to the CSV file.
    :param max_lines: Maximum number of lines to read (default is 1000).
    :return: A list of lists, where each inner list represents a split line.
    """
    split_lines = []
    
    with open(file_path, mode='r', newline='', encoding='utf-8') as file:
        csv_reader = csv.reader(file)
        for i, row in enumerate(csv_reader):
            if i >= max_lines:
                break
            split_lines.append(row)
    
    return split_lines

# Example usage
# Assuming the file is in 'MyDrive' within your Google Drive
file_path = '/content/drive/MyDrive/lego_setsHB.csv'  # Update with the correct path in your Drive
split_lines = read_and_split_csv(file_path, max_lines=1000)

# Print the first 1000 split lines
for line in split_lines:
    print(line)
