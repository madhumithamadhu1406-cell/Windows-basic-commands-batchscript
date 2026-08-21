# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:<img width="387" height="53" alt="image" src="https://github.com/user-attachments/assets/fd59fbe2-9168-4e96-8eb5-779629c52359" />


Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
mkdir my-folder
<img width="387" height="53" alt="image" src="https://github.com/user-attachments/assets/59aef289-2dc5-415d-a63d-76576537ad66" />

Remove the directory "my-folder"

## COMMAND AND OUTPUT
rmdir my-folder
<img width="408" height="50" alt="image" src="https://github.com/user-attachments/assets/a813ec2a-6f5a-4308-be91-00d830e74310" />


Create the file Rose.txt

## COMMAND AND OUTPUT
type nul > Rose.txt
<img width="439" height="55" alt="image" src="https://github.com/user-attachments/assets/f06680c8-db5a-4fa9-a1d7-e98934dcf486" />

Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
echo Hello World > hello.txt
<img width="558" height="52" alt="image" src="https://github.com/user-attachments/assets/60109493-e8f5-4988-9f63-f5275148d24b" />

Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
copy hello.txt hello1.txt
<img width="497" height="69" alt="image" src="https://github.com/user-attachments/assets/4bcd618c-74f2-434e-b916-b78c569ea971" />

Remove the file hello1.txt

## COMMAND AND OUTPUT
del hello1.txt
<img width="390" height="49" alt="image" src="https://github.com/user-attachments/assets/7a7e6551-f4a1-448f-a6b5-0033f714a6b5" />

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
dir hello1.txt
<img width="438" height="182" alt="image" src="https://github.com/user-attachments/assets/82fcb8dd-c538-4d33-a4f7-510e63257a0f" />

List out all the associated file extensions 

## COMMAND AND OUTPUT
assoc
<img width="625" height="880" alt="image" src="https://github.com/user-attachments/assets/7e9b24e9-593c-4b79-bb37-3fb91ee2fc1b" />


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
fc hello.txt Rose.txt
<img width="536" height="159" alt="image" src="https://github.com/user-attachments/assets/ce462b2a-8f8b-4828-8324-0c0a2cdab604" />

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".





## OUTPUT

<img width="494" height="77" alt="image" src="https://github.com/user-attachments/assets/40107a4f-aacb-4c26-a24b-fde90839591e" />


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
## CODE
```
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE
:END
echo Thank you!
pause
```


## OUTPUT
<img width="656" height="202" alt="image" src="https://github.com/user-attachments/assets/a9d1652d-f906-43c7-b732-9be67f3aa74a" />




Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```


## OUTPUT



<img width="457" height="165" alt="image" src="https://github.com/user-attachments/assets/80d37636-3fff-4289-8824-5e1290954af0" />

Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
```
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
```
## OUTPUT

<img width="422" height="52" alt="image" src="https://github.com/user-attachments/assets/87c47278-073c-4854-807a-e6898402c932" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
```
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU
:EXIT
echo Goodbye!
pause
exit
```

## OUTPUT
<img width="410" height="192" alt="image" src="https://github.com/user-attachments/assets/e2b7d3c0-425b-48cc-b6af-e2310f9a9fdd" />
<img width="441" height="203" alt="image" src="https://github.com/user-attachments/assets/1f3b1a73-94e0-415c-8ed2-fbeea370546d" />
<img width="431" height="197" alt="image" src="https://github.com/user-attachments/assets/e5714974-5a8e-4170-86e9-be5f0151f17a" />



# RESULT:
The commands/batch files are executed successfully.

