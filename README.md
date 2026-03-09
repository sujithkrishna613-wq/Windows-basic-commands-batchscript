# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
```
mkdir my-folder
```
<img width="917" height="40" alt="image" src="https://github.com/user-attachments/assets/325af40e-bec1-448c-ac8d-2033e2bec766" />

Remove the directory "my-folder"

## COMMAND AND OUTPUT
```
rmdir my-folder
```
<img width="791" height="50" alt="image" src="https://github.com/user-attachments/assets/e81fb3d0-42d7-4308-b7bd-1546ad74eba0" />


Create the file Rose.txt

## COMMAND AND OUTPUT
```
type nul > Rose.txt
```
<img width="567" height="35" alt="image" src="https://github.com/user-attachments/assets/35d93867-354d-42bd-aa68-e392076906cd" />

Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
```
echo Hello World > hello.txt
```
<img width="792" height="41" alt="image" src="https://github.com/user-attachments/assets/89346e6f-a9b5-4968-977f-803b3ce10d61" />
Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
```
copy hello.txt hello1.txt
```
<img width="620" height="61" alt="image" src="https://github.com/user-attachments/assets/bc38d95f-0e52-4cdf-8f04-4be0a58c3513" />



Remove the file hello1.txt

## COMMAND AND OUTPUT
```
del hello1.txt
```
<img width="493" height="36" alt="image" src="https://github.com/user-attachments/assets/58b8e2fa-87cf-4de6-965c-5ae2086dd4db" />

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
```
dir hello1.txt
```
<img width="525" height="210" alt="image" src="https://github.com/user-attachments/assets/9c17ca22-fb4c-4a8e-a219-b97e3cb9c6ff" />
List out all the associated file extensions 

## COMMAND AND OUTPUT
```
assoc
```


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
```
fc hello.txt Rose.txt
```
<img width="580" height="173" alt="image" src="https://github.com/user-attachments/assets/b2830390-d2b3-4ab7-a368-1328d738f277" />


## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
```
set name=John
echo Hello, %name%
pause
```





## OUTPUT
<img width="550" height="65" alt="image" src="https://github.com/user-attachments/assets/002e8814-d8f7-49ac-902e-1525f56f7cd5" />



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
<img width="768" height="237" alt="image" src="https://github.com/user-attachments/assets/942c2aa4-6419-4d7b-ba73-f674538672f2" />



Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
## CODE
```@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```

## OUTPUT
<img width="500" height="182" alt="image" src="https://github.com/user-attachments/assets/fa561261-56da-4a01-984f-30763b6ba3be" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
## CODE
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
<img width="501" height="57" alt="image" src="https://github.com/user-attachments/assets/76d31023-469b-4037-858e-c4e6dbbd5df4" />


Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
## CODE
```
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


## OUTPUT1

<img width="514" height="238" alt="image" src="https://github.com/user-attachments/assets/eb8e107e-6640-4a9a-ad3d-d4f8e1db97f8" />

## OUTPUT2

<img width="515" height="233" alt="image" src="https://github.com/user-attachments/assets/00da6e62-960e-43dd-9931-96e86a0ba69e" />

## OUTPUT3

<img width="522" height="232" alt="image" src="https://github.com/user-attachments/assets/4c507170-83cc-45eb-95bc-5bbb7a133393" />



# RESULT:
The commands/batch files are executed successfully.

