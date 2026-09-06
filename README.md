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

<img width="847" height="33" alt="image" src="https://github.com/user-attachments/assets/47a0e684-b8df-44d1-8eae-9a17bb6829f2" />


## Remove the directory "my-folder"

**COMMAND AND OUTPUT**

<img width="942" height="25" alt="image" src="https://github.com/user-attachments/assets/7e4c661d-21a8-48a6-a1a7-4fb9cfb44fe9" />

## Create the file Rose.txt

**COMMAND AND OUTPUT**

<img width="962" height="27" alt="image" src="https://github.com/user-attachments/assets/234128f4-b446-4433-bca0-ab855253fd36" />

## Create the file hello.txt using echo and redirection

 __COMMAND AND OUTPUT__

<img width="1047" height="35" alt="image" src="https://github.com/user-attachments/assets/912a35ac-eb53-4483-a3d7-6d0b5b2f3603" />

## Copy the file hello.txt into the file hello1.txt

__COMMAND AND OUTPUT__
<img width="1050" height="47" alt="image" src="https://github.com/user-attachments/assets/d160240e-4b96-4bdb-804c-05f2ceec2df6" />

## Remove the file hello1.txt

 __COMMAND AND OUTPUT__

<img width="903" height="32" alt="image" src="https://github.com/user-attachments/assets/d4a2daf2-0f72-4d85-801b-bc024d42f404" />

## List out the file hello1.txt in the current directory

 __COMMAND AND OUTPUT__
<img width="1047" height="137" alt="image" src="https://github.com/user-attachments/assets/b0a38dd8-ce67-41d2-a4ad-633815386302" />



## List out all the associated file extensions 

__COMMAND AND OUTPUT__
<img width="835" height="777" alt="image" src="https://github.com/user-attachments/assets/094a6b58-9979-457f-814c-33469b9ffd32" />

<img width="747" height="772" alt="image" src="https://github.com/user-attachments/assets/cd2a141d-2c11-4cd1-acc4-ea6f03175093" />

<img width="750" height="731" alt="image" src="https://github.com/user-attachments/assets/fdff0526-6347-47c8-9730-40d9c489886a" />


<img width="711" height="670" alt="image" src="https://github.com/user-attachments/assets/43e23db3-575a-4fca-a86f-9c45d478f047" />

<img width="757" height="727" alt="image" src="https://github.com/user-attachments/assets/aa40acd7-9a89-4fcf-a57f-5a1de4405eef" />

<img width="762" height="762" alt="image" src="https://github.com/user-attachments/assets/ac153219-5273-41cf-a955-75481871da86" />

<img width="738" height="735" alt="image" src="https://github.com/user-attachments/assets/1f84f21f-b224-4ef3-b864-0a4966c52675" />

<img width="638" height="727" alt="image" src="https://github.com/user-attachments/assets/acfa3308-9444-4df5-b655-9f81394c12b7" />
<img width="621" height="642" alt="image" src="https://github.com/user-attachments/assets/2dc487e9-949a-46f9-83c9-0c0f4af78265" />
<img width="642" height="766" alt="image" src="https://github.com/user-attachments/assets/76f25fc9-91b3-449b-9c17-595babbaa3f3" />

## Compare the file hello.txt and rose.txt

 __COMMAND AND OUTPUT__
<img width="950" height="102" alt="image" src="https://github.com/user-attachments/assets/8c83fbbd-493b-4c34-bd3a-02d27f9dbd31" />





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

<img width="962" height="67" alt="image" src="https://github.com/user-attachments/assets/815e81a8-aee1-461a-9d43-3f96a2cbcbba" />

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

<img width="942" height="180" alt="image" src="https://github.com/user-attachments/assets/03faac36-3191-453d-bccc-40d2886fda0b" />


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

<img width="952" height="140" alt="image" src="https://github.com/user-attachments/assets/49f65cbf-7f25-4095-b0c7-1e23efa9a07a" />


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
<img width="937" height="67" alt="image" src="https://github.com/user-attachments/assets/ccb2a6aa-2341-4f12-b03e-ddc140b97ef5" />


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
<img width="652" height="162" alt="image" src="https://github.com/user-attachments/assets/3b7904a5-2b88-4a02-afc9-04dc975d118a" />


<img width="652" height="245" alt="image" src="https://github.com/user-attachments/assets/1151a193-8dfa-41bb-8119-efefd54b39ba" />

<img width="526" height="187" alt="image" src="https://github.com/user-attachments/assets/66b9bbe3-3455-421d-b9cc-6f6f554386d4" />

# RESULT:
The commands/batch files are executed successfully.
