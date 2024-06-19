# Update-a-file-through-a-Python-algorithm

## Activity Overview

In this activity, you will create a new portfolio document to demonstrate your experience using Python to develop algorithms that involve opening files and parsing their contents. You can add this document to your cybersecurity portfolio, which you can share with prospective employers or recruiters. To review the importance of building a professional portfolio and options for creating your portfolio, read 
Create a cybersecurity portfolio
.

To create your portfolio document, you will review a scenario and follow a series of steps. This scenario is connected to the 
Create another algorithm
 lab that you have just completed. You will explain the code you developed in that lab, and this will help you prepare for future job interviews and other steps in the hiring process.

Be sure to complete this activity before moving on. The next course item will provide you with a completed exemplar to compare to your own work. 

Scenario

Review the following scenario. Then complete the step-by-step instructions.

You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.

Your task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, you should remove those IP addresses from the file containing the allow list.

Note: This scenario involves developing the same algorithm that is developed in Tasks 2-7 of the 
Create another algorithm
 lab. (You do not need to reference Task 1 and Tasks 8-10 of the lab to complete this portfolio activity.) You should revisit the lab to get screenshots to include in your portfolio document. 

Step-By-Step Instructions

Follow the instructions to complete each step of the activity. Then, answer the 9 questions at the end of the activity before going to the next course item to compare your work to a completed exemplar.


Step 1: Access the template
To use the template for this course item, click the link and select Use Template. (In this step, you will just open the template. More instructions for how to use the template will be included in later steps.)

Link to template: 
Algorithm for file updates in Python

OR

If you don’t have a Google account, you can download the template directly from the following attachment.


The following supporting material will help you complete this activity. The document Instructions for including Python code provides instructions and best practices for including samples of Python code in your portfolio activity. Keep it open as you proceed to the next steps. 

To use the supporting material for this course item, click the link and select Use Template. 

Link to supporting material: 
Instructions for including Python code

OR

If you don’t have a Google account, you can download the supporting material directly from the following attachment.


The file that you want to open is called "allow_list.txt". Assign a string containing this file name to the import_file variable. Then, use a with statement to open it. Use the variable file to store the file while you work with it inside the with statement.

Describe the Python syntax, functions, and keywords you need to accomplish this in the Open the file that contains the allow list section of the Algorithm for file updates in Python template. In the Task 2 section of Create another algorithm lab, take a screenshot of this portion of your code. Or, type this code directly into the template.

Next, use the .read() method to convert the contents of the allow list file into a string so that you can read them. Store this string in a variable called ip_addresses.

Describe the Python syntax, functions, and keywords you need to accomplish this in the Read the file contents section of the Algorithm for file updates in Python template. In the Task 3 section of the Create another algorithm lab, take a screenshot of this portion of your code. Or, type this code directly into the template.

In order to remove individual IP addresses from the allow list, the IP addresses need to be in a list format. Therefore, use the .split() method to convert the ip_addresses string into a list.

Describe the Python syntax, functions, and keywords you need to accomplish this in the Convert the string into a list section of the Algorithm for file updates in Python template. In the Task 4 section of the Create another algorithm lab, take a screenshot of this portion of your code. Or, type this code directly into the template.

A second list called remove_list contains all of the IP addresses that should be removed from the ip_addresses list. Set up the header of a for loop that will iterate through the remove_list. Use element as the loop variable.

Describe the Python syntax, functions, and keywords you need to accomplish this in the Iterate through the remove list section of the Algorithm for file updates in Python template. In the Task 5 section of the Create another algorithm lab, take a screenshot of this portion of your code. Or, type this code directly into the template.

In the body of your iterative statement, add code that will remove all the IP addresses from the allow list that are also on the remove list. First, create a conditional that evaluates if the loop variable element is part of the ip_addresses list. Then, within that conditional, apply the .remove() method to the ip_addresses list and remove the IP addresses identified in the loop variable element. 

Describe the Python syntax, functions, and keywords you need to accomplish this in the Remove IP addresses that are on the remove list section of the Algorithm for file updates in Python template. In the Task 6 section of the Create another algorithm lab, take a screenshot of this portion of your code. Or, type this code directly into the template.

In addition, include a sentence that explains that applying the .remove() method in this way is possible because there are no duplicates in the ip_addresses list. 

Now that you have removed these IP addresses from the ip_address variable, you can complete the algorithm by updating the file with this revised list. To do this, you must first convert the ip_addresses list back into a string using the .join() method. Apply .join() to the string "\n" in order to separate the elements in the file by placing them on a new line.

Then, use another with statement and the .write() method to write over the file assigned to the import_file variable.

Describe the Python syntax, functions, and keywords you need to accomplish this in the Update the file with the revised list of IP addresses section of the Algorithm for file updates in Python template. In the Task 7 section of the Create another algorithm lab, take a screenshot of this portion of your code. Or, type this code directly into the template.

To finalize the document and make its purpose clear to potential employers, be sure to complete the Project description and Summary sections of the Algorithm for file updates in Python template. 

In the Project description section, give a general overview of the scenario and what you accomplished in Python. Write three to five sentences.

In the Summary section, provide a short summary of the algorithm by highlighting its main components. Write four to six sentences.

## My Technical Solutions

### Algorithm for File Updates in Python

#### Project Description
In this scenario, you are tasked with maintaining an allow list of IP addresses for a healthcare company. Employees' access to restricted content is managed by this list, which is regularly updated. Your goal is to create a Python algorithm to check if any IP addresses on a remove list are present in the allow list and to remove them if they are. This ensures that only authorized IP addresses have access to the restricted subnetwork.

#### Open the File that Contains the Allow List
To open the file `allow_list.txt`, we use the `with` statement, which ensures the file is properly closed after its suite finishes.

```python
import_file = "allow_list.txt"
with open(import_file, "r") as file:
    ip_addresses = file.read()
```

This code snippet assigns the filename to `import_file` and opens the file in read mode. The file's contents are then read and stored in the `ip_addresses` variable.

#### Read the File Contents
Using the `.read()` method, the contents of the file are converted into a string.

```python
ip_addresses = file.read()
```

The `read()` method reads the entire file content into a single string, which is stored in the variable `ip_addresses`.

#### Convert the String into a List
To manipulate the IP addresses individually, the string is converted into a list using the `.split()` method.

```python
ip_addresses = ip_addresses.split()
```

The `split()` method divides the string into a list of IP addresses based on whitespace by default.

#### Iterate Through the Remove List
Set up a `for` loop to iterate through the `remove_list` and use `element` as the loop variable.

```python
remove_list = ["192.168.1.1", "192.168.1.2"]  # Example remove list
for element in remove_list:
```

This code snippet creates a loop that iterates through each item in the `remove_list`.

#### Remove IP Addresses That Are on the Remove List
Within the loop, a conditional statement checks if `element` is in `ip_addresses`. If true, the `.remove()` method deletes it.

```python
if element in ip_addresses:
    ip_addresses.remove(element)
```

The `remove()` method removes the first matching element from the list. This is possible because there are no duplicates in the `ip_addresses` list.

#### Update the File with the Revised List of IP Addresses
Convert the updated list back into a string using `.join()`, then write it back to the file.

```python
ip_addresses = "\n".join(ip_addresses)
with open(import_file, "w") as file:
    file.write(ip_addresses)
```

The `join()` method concatenates the list into a string with each element separated by a newline character. The `write()` method overwrites the file with the updated list.

#### Summary
This algorithm efficiently manages the allow list by removing IP addresses listed in the remove list. It starts by reading the allow list file and converting its contents into a manageable list format. It then iterates through the remove list, conditionally removing any matching IP addresses from the allow list. Finally, it updates the original file with the revised list. This ensures that only authorized IP addresses have access to restricted content, maintaining the security of the healthcare company's network.

---
