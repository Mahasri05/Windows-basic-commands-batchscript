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
![image](https://github.com/user-attachments/assets/cd28bba8-839d-436e-9b27-3d8c95d53df7)




Remove the directory "my-folder"

## COMMAND AND OUTPUT
```
rmdir my-folder
```
![image](https://github.com/user-attachments/assets/ee7e84c3-8c46-46e3-a6f5-94f7d517c1b6)


Create the file Rose.txt

## COMMAND AND OUTPUT
```
dir Rose.txt
```
![image](https://github.com/user-attachments/assets/fa752fec-85fe-4e2c-8ddb-d1f830d4771a)



Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
```
echo “hello world” > hello.txt
type hello.txt
```
![image](https://github.com/user-attachments/assets/a63be68d-53b0-49d2-8703-45a6a8b8c676)

Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
```
copy hello.txt hello1.txt
```
![image](https://github.com/user-attachments/assets/1f9a34b0-953a-4592-9882-11781895042d)


Remove the file hello1.txt

## COMMAND AND OUTPUT
```
del hello1.txt
```
![image](https://github.com/user-attachments/assets/37c3d571-c3bb-4024-8afd-eb206b5d36df)

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
```
dir hello1.txt
```
![image](https://github.com/user-attachments/assets/c7b14d65-d2ac-4efa-a373-86fefb81c74d)

List out all the associated file extensions 

## COMMAND AND OUTPUT
```
assoc | more
```
![image](https://github.com/user-attachments/assets/d979a342-a28f-40ee-8678-2354a2fb528f)


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
```
fc hello.txt Rose.txt
```
![image](https://github.com/user-attachments/assets/d2dbef13-1a79-44aa-9e03-0fa2676ed7b3)



## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

```
@echo off
set name=John
echo Hello, %name%
pause
```



## OUTPUT
![image](https://github.com/user-attachments/assets/a0a85ea3-70a7-4202-85ae-cb783f3fadca)



```
Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
```
```
@echo off
:loop
set /p num=Enter a number: 
set /a rem=%num% %% 2

if %rem%==0 (
    echo %num% is Even
) else (
    echo %num% is Odd
)

:ask
set /p ans=Do you want to check another number? (Y/N): 
if /I "%ans%"=="Y" goto loop
if /I "%ans%"=="N" goto end
echo Invalid input. Please enter Y or N.
goto ask

:end
echo Thank you!
pause
```



## OUTPUT

![image](https://github.com/user-attachments/assets/47f39df8-bb39-4067-9aec-34ffd968ebca)



Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
```
@echo off
for /L %%i in (1,1,5) do (
    echo Number: %%i
)
pause
```



## OUTPUT
![image](https://github.com/user-attachments/assets/24bdf348-3a67-4987-8065-d0e5afd79cc5)




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.
```
Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
```
```
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause
```

## OUTPUT
![image](https://github.com/user-attachments/assets/21219077-4bbd-4aab-8119-3dce4ae78b39)


```
Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
```
```
@echo off
:menu
cls
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option (1-3): 

if "%choice%"=="1" goto hello
if "%choice%"=="2" goto create
if "%choice%"=="3" goto exit
echo Invalid choice.
pause
goto menu

:hello
echo Hello, World!
pause
goto menu

:create
echo This is a new file > newfile.txt
echo File newfile.txt created.
pause
goto menu

:exit
echo Goodbye!
pause
exit
```


## OUTPUT
![image](https://github.com/user-attachments/assets/2ec6dace-3d05-4fd0-8fc5-87fc441b49c9)




# RESULT:
The commands/batch files are executed successfully.

