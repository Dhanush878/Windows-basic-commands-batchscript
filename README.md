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

---
## Create a directory named "my-folder"

 __COMMAND AND OUTPUT__

![image](https://github.com/user-attachments/assets/310adc41-c138-44ad-a796-c97377e522eb)

## Remove the directory "my-folder"

**COMMAND AND OUTPUT**

![image](https://github.com/user-attachments/assets/60c7ac22-e4e3-4562-9c9d-e4f478a57779)
## Create the file Rose.txt

**COMMAND AND OUTPUT**

![image](https://github.com/user-attachments/assets/9ae68240-33be-4c11-80cb-19a187bd0147)
## Create the file hello.txt using echo and redirection

 __COMMAND AND OUTPUT__

![image](https://github.com/user-attachments/assets/7e64d07e-b82f-447f-ac4f-708c88cb896a)
## Copy the file hello.txt into the file hello1.txt

__COMMAND AND OUTPUT__
![image](https://github.com/user-attachments/assets/72dd3bac-ce2e-4cac-9465-74196eea314c)
## Remove the file hello1.txt

 __COMMAND AND OUTPUT__

![image](https://github.com/user-attachments/assets/06b7d7d2-d56e-4636-8bb5-1e7e7fb0c401)
## List out the file hello1.txt in the current directory

 __COMMAND AND OUTPUT__

![image](https://github.com/user-attachments/assets/77e3f1c2-ecc9-4e6e-be84-d9d7b5b4fd3e)

## List out all the associated file extensions 

__COMMAND AND OUTPUT__
![image](https://github.com/user-attachments/assets/4f2ab674-580b-43d2-8c81-4d504d68588a)
![image](https://github.com/user-attachments/assets/6a99074a-e6d6-44b1-9f0c-a5eedd06aa95)
![image](https://github.com/user-attachments/assets/a93a8647-5498-46ac-aa03-9288dde1ead2)
![image](https://github.com/user-attachments/assets/30428284-b1a0-42ad-bf5f-75a66eaaf5d8)
![image](https://github.com/user-attachments/assets/ad8b52dd-e90d-4b59-b998-4c2104aee291)
![image](https://github.com/user-attachments/assets/8223039f-e24c-4dd3-a599-ccfee5ba78c2)
![image](https://github.com/user-attachments/assets/1aa19e88-2f62-478d-b25c-fa6d508d746e)
![image](https://github.com/user-attachments/assets/4b154997-30b5-4a7d-8659-26fd84f6c38f)
![image](https://github.com/user-attachments/assets/78b8e4f0-73ab-4650-81f8-8775ccb3e445)
![image](https://github.com/user-attachments/assets/da2c5c29-a7d4-4f2b-ade7-8666676f3423)
![image](https://github.com/user-attachments/assets/f0e134ea-ea77-4c98-8076-beaf3034baae)
## Compare the file hello.txt and rose.txt

 __COMMAND AND OUTPUT__
![image](https://github.com/user-attachments/assets/a06daafa-850b-450b-b14c-724a17bf44f9)




## Exercise 2: Advanced Batch Scripting
__1__.Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="Sudharsan" and display as "Hello, Sudharsan".

### BATCH PROGRAM

``` batch
@echo off
set name=Sudharsan 
echo Hello, %name%
pause
```



### OUTPUT
![image](https://github.com/user-attachments/assets/ca4c5061-c9fd-4445-98c5-645f7f9db851)


__2__.Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

### BATCH PROGRAM
``` batch
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

### OUTPUT
![image](https://github.com/user-attachments/assets/0e635a8d-df3c-4156-8f02-5252271dbaae)


__3__.Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

### BATCH PROGRAM

``` batch
@echo off
for /L %%i in (1,1,5) do (
    echo Number: %%i
)
pause
```

### OUTPUT

![image](https://github.com/user-attachments/assets/44e93880-ee7b-44d0-b2b8-35e1bfa54c65)


__4__.Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

__Instructions:__
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

### BATCH PROGRAM

``` batch
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause
```

### OUTPUT
![image](https://github.com/user-attachments/assets/e3947d72-0ce0-4dc7-9ba3-4eb6d3ffd9e5)

__5__.Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

### BATCH PROGRAM

``` batch
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

### OUTPUT
![image](https://github.com/user-attachments/assets/09cc0a17-592e-45cd-bfbf-0763a3bd1946)

![image](https://github.com/user-attachments/assets/86e21d7d-3e74-44d6-8fcf-54c38ef296a1)

![image](https://github.com/user-attachments/assets/800fcd82-0399-400a-a582-e042315c2f51)
# RESULT:
The commands/batch files are executed successfully.
