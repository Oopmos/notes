# Linux
คือ UNIX clone ที่เป็น open source และถูกพัฒนาโดย community จึงทำให้ระบบสามารถรองรับการทำงานได้พร้อมกันหลายคน

ทำไมคนที่ทำงานด้านการเขียนโค้ดถึงใช้ Linux กันเยอะ เพราะ
1. เป็น Open source operating system (ฟรี)
2. Access to source code สามารถปรับแต่งระบบปฏิบัติการได้อย่างไร้ขีดจำกัด
3. Highly secure ไม่มีปัญหาเรื่อง Virus หรือ Malware และตัว OS ยังมีความปลอดภัยสูงเนื่องจาก Open source ทุกคนจึงสามารถเข้าไปตรวจสอบได้
4. Runs faster 

## Kernel

โปรแกรมที่ทำหน้าที่ในการแบ่งทรัพยากรณ์ของเครื่อง และประสานงานส่วนต่าง ๆ ภายในคอมพิวเตอร์เรียกว่า operating system (OS) หรือ Kernel ส่วนที่ผู้ใช้งานไว้ติดต่อกับ OS เรียกว่า Shell

Kernel Applications : MAC OS

## Command Line Interface (CLI)
เป็น Text-base inteface ที่ใช้โต้ตอบกับ software และใช้ operating system ด้วยการพิมพ์คำสั่งไปที่หน้าจอ และได้รับผลลัพธ์มาท่งหน้าจอเช่นกัน

มีประโยชน์หลายด้าน เช่น
- Scale up (ขยาย infrastructure ทั้ง compute, storage หรือ Network ให้ขึ้น เพื่อรองรับผู้คนที่เข้ามาใช้งานได้มากขึ้น)
- Control (สร้าง script หรือทำ automation)
- Use less memory

### Command Line Interface (CLI) VS Graohical User Interface (GUI)
CLI
- Text-based interface มีแต่ตัวอักษร
- ใช้งานยาก
- ระบบเร็วกว่า
- ควบคุมได้มากกว่า

GUI
- Visual-based interface มีรูปภาพช่วยให้เข้าใจง่าย เช่น icon, menu
- ใช้งานง่าย
- ระบบช้ากว่า เพราะทุกอย่างที่ลบไม่ได้ลบโดยถาวร
- ควบคุมได้น้อยกว่า

# Command Line Essentials
ถ้าเป็นสิ่งที่แสดงออกทางหน้าจอจะให้ขึ้นต้นด้วย >
clear หน้าจอโดยการพิมพ์ clear หรือกด crtl + L
## Directory
### cd (change directory)
เปลี่ยน directory ไปยัง path ที่เลือก

```bash
cd [Path]

cd /home/username
```

สัญลักษณ์ที่ใช้บ่อย
~ -> Home (~ Tilde)
/ -> Root (/ Slash)
.  -> Current Directory
.. -> Parent Directory

### pwd (print working directory)
แสดง directory ปัจจุบัน

```bash
pwd

> /home/username
```

### ls (list)
ดูไฟล์ และโฟลเดอร์ทั้งหมดใน directory ปัจจุบัน หรือใน directory ที่กำหนดก็ได้

```bash
ls

ls /home/

ls --help # เพื่อดูข้อมูลเพิ่ม
```

| Mandatory argument  | สิ่งที่เกิดขึ้น                               |
|:------------------- | --------------------------------------------- |
| -l                  | โชว์ข้อมูลไฟล์มากขึ้น                         |
| -h (human readable) | อ่านไฟล์เป็น KB, MB, GB                       |
| -a                  | โชว์ไฟล์ที่ซ่อน (ไฟล์ที่ซ่อนขึ้นต้นด้วยจุด .) |

## Manage files
### cp (copy)
copy จากไฟล์ต้นทาง ไปวางที่ปลายทาง

```bash
cp [SOURCE] [DESTINATION]

cp hello.txt home/new_folder/
```

copy ทั้งไฟล์ในโฟลเดอร์ทั้งหมดไปวางต้องใช้ -r (recursive)
```bash
cp -r home/new_folder/ home/new_folder2 # ย้ายไฟล์ทั้งหมดใน home/new_folder/ ไปไว้ใน home/new_folder2
```

### mv (move)
ย้าย หรือใช้เปลี่ยนชื่อไฟล์

```bash
mv [SOURCE] [DESTINATION]
mv hello.txt home/new_folder/ # ย้าย hello.txt ไปไว้ใน home/new_folder/
mv home/new_folder2 good_name # เปลี่ยนชื่อ folder จาก new_folder2 เป็น good_name
```
### rm (remove)
ลบไฟล์

```bash
cd home/good_name # ย้ายไปที่ home/good_name
rm hello.txt # ลบไฟล์

cd ~ # กลับไปที่ home
rm -r good_name # ลบโฟลเดอร์ good_name
```
## Print
### echo (print ในเวอร์ชั่น Linux)
แสดงออกมาทางหน้าจอ

```bash
echo "hello world"
> hello world
```
## Create / Read file
### cat (concatenate)
อ่านไฟล์ (แสดงข้อความในไฟล์ด้านล่าง)

```bash
cat hello.txt
> hello
```

### less
อ่านไฟล๋ (แสดงข้อความในไฟล์ เปิดหน้าต่างขึ้นมาใหม่เลย)
กด Q เพื่อกลับไปหน้าเดิม
กด space bar เพื่อดูหน้าถัดไป

### grep
ค้นหาบรรทัดในไฟล์ที่ตรงตามเงื่อนไข เช่น

```bash
cat test1
> Ant
> Bee
> Cat
> Dog
> Fly

grep a test1 # ค้นหาข้อความที่มี 'a' ในนั้น
> Cat
> Man

grep mv --help | gerp -verbose # แสดงข้อมูลเดี่ยวกับคำสั่ง mv เพิ่ม แต่เอาแค่ข้อความที่มีคำว่า verbose
> -v, --verbose explain what is being done
```

### touch
สร้างไฟล์เปล่าใน directory ที่อยู่ตอนนี้

```bash
touch [FILENAME]

touch blank.txt
cat blank.txt # อ่าน blank.txt แต่ไม่ขึ้นอะไร เพราะเป็นไฟล์เปล่า
```

### mkdir (make directory)
สร้างโฟลเดอร์ใหม่ใน directory ที่อยู่ตอนนี้

```bash
mkdir [DIRECTORY_NAME]

mkdir new_folder
```

สามารถสร้างโฟลเดอร์ซ้อนกันหลายชั้นได้ โดยใช้ -p (p : parent คือสร้าง parent ถ้าไม่มี)

```bash
mkdir -p new_folder/in/folder
```


## Additional command
### chmod
เปลี่ยน permission ของไฟล์

```bash
chmod ugo [FILENAME] # u = user, g = user group, o = other user

chmod +r test.sh # read

chmod +w test.sh # write

chmod +x test.sh # excute

chmod 777 test.sh # ให้ทุกคนมีทุกมีสิทธิ์ read + write + excute
```

ตัวเลขที่ใช้เป็นเลขฐาน 8 ใช้ในการระบุสิทธิ์
|  number   | permission |
|:---------:|:----------:|
|     0     |  nothing   |
|     1     |  execute   |
|     2     |   write    |
|  3 (2+1)  |    w+x     |
|     4     |    read    |
|  5 (4+1)  |    r+x     |
|  6 (4+2)  |    r+w     |
| 7 (4+2+1) | r+w+x           |

### man + help
เปิด Manual ขึ้นมา
กด H เพื่อดูสรุป
กด Q เพื่อออก


# Shell Script Basic
## Shell
คือโปรแกรมสำหรับแปลคำสั่งที่แปลคำสั่งที่ถูกป้อนโดยผู้ใช้แปลงเป็นภาษาที่ Kernel เข้าใจ

## Shell Script
คอนเซ็ปต์โดยทั่วไปแล้วมันคือลิสต์ของคำสั่ง โดยจะถูกเรียงตามลำดับการเรียกใช้งาน Shell Script ที่ดีควรมีการคอมเมนต์เพื่ออธิบายเพิ่มเพื่อให้คนมาอ่านเข้าใจ คอมเมนต์ได้ง่ายด้วยการ # comment

## Type of shell
แบ่งได้เป็น 2 ประเภทหลัก ๆ ได้แก่
1. Bourne Shell Types
- Bourne Shell (.sh)
- Korn Shell
- Bourne-Again Shell
- PDSIX Shell

2. C Shell Types
- C Shell
- TENEX/TOPS C Shell
- Z Shell

## How it works
เริ่มด้วยการสร้างไฟล์ด้วย nano editor

```bash
#เริ่มด้วย shebang line (#!) ตามด้วย full path ไปที่ interpreter
#! /bin/sh

#Author : P
#Script is as follows

echo "What is your Name?" 
read PERSON #เก็บ user input ไว้ในตัวแปร PERSON
echo "Hello. $PERSON" #เรียกตัวแปรเริ่มด้วย $
```

# Using Variable
## Variable
คือ string ที่เราใส่ค่าเข้าไป โดยค่าที่ใส่เข้าไปสามารถเป็นตัวเลข, ตัวอักษร และประเภทของข้อมูลอื่น ๆ

## Variable Types
### Local Variable
เป็นตัวแปรที่ใช้ได้แค่ใน shell script นี้ หากไปสร้าง shell script ใหม่จะไม่สามารถใช้งานได้ ตัวแปรถูกเซ็ทที่ command promt

### Environmental Variable
เป็นตัวแปรที่ต้องใช้เพื่อ shell script ทำงานได้อย่างถูกต้อง

### Shell Variable
หรือ Global Variable เป็นตัวแปรพิเศษถูกสร้างขึ้นที่ shell และต้องใช้เพื่อที่จะให้โปรแกรมทำงานได้อย่างถูกต้อง ในบางครั้งตัวแปรเหล่านี้สามารถเป็นได้ทั้ง Environmental Variable หรือ Local Variable ก็ได้

## Using Variable
### Defining Variables

```shell
#!/bin/sh

# variable_name=variable_value ห้ามเคาะเว้นตรงหน้า-หลัง = เด็ดขาด

NAME="Punyapat Sompoo" # เป็น Scalar Variable (ตัวแปรที่เก็บค่าได้ทีละค่า)
```

Read only variable คือไม่สามารถเปลี่ยนค่าได้แล้ว เช่น

```bash
#!/bin/sh

NAME="Punyapat Sompoo"
read only NAME
NAME="WIN" # เวลา run จะขึ้น error
```

Unsetting Variable (Delete Variable)

```bash
#!/bin/sh

NAME="Punyapat Sompoo"
unset NAME
echo $NAME # เวลารันจะไม่ขึ้นอะไรเลย
```

### Special Variables

```bash
#!/bin/sh

echo "File name: $0"
echo "First Parameter: $1"
echo "Second Parameter: $2"
echo "Quoted Value: $**"
echo "Quoted Value: $@"
echo "No. of Parameter: $#"
```

```
# input
Punyapat Sompoo

# output
File name: ./variable.sh
First Parameter: Punyapat
Second Parameter: Sompoo
Quoted Value: Punyapat Sompoo
Quoted Value: Punyapat Sompoo
No. of Parameter: 2

# แต่ถ้าใส่ "" ครอบ
"Punyapat Sompoo"

# output
File name: ./variable.sh
First Parameter: Punyapat Sompoo
Second Parameter:
Quoted Value: Punyapat Sompoo
Quoted Value: Punyapat Sompoo
No. of Parameter: 1

# ใส่ "" แยกกัน
"Punyapat" "Sompoo"
File name: ./variable.sh
First Parameter: Punyapat 
Second Parameter: Sompoo
Quoted Value: Punyapat Sompoo
Quoted Value: Punyapat Sompoo
No. of Parameter: 2
```

### Command Line Arguments

```bash
#!/bin/sh

for TOKEN in $*
do
	echo $TOKEN
done
```

### Special Parameters

```bash
# input
./variable.sh Punyapat wishes you have a good time

# output
Punyapat
wishes
you
have
a
good
time
```

### Exit Status

```bash
echo $? # ถ้าได้ 0 แสดงว่ารันผ่าน ถ้าไม่เป็น 1
```

# Basic Operators
กำหนดให้ a=10 b=20
## Arithmatic Operators

| Operator           | Purpose    | Example                      |
| ------------------ | ---------- | ---------------------------- |
| + (Addition)       | บวก        | 'expr $a + $b' จะได้ 30      |
| - (Subtraction)    | ลบ         | 'expr $a - $b' จะได้ -10     |
| * (Multiplication) | คูณ        | 'expr $a * $b' จะได้ 200     |
| / (Division)       | หาร        | 'expr $b / $a' จะได้ 2       |
| % (Modulus)        | หารหาเศษ   | 'expr $b % $a' จะได้ 0       |
| = (Assignment)     | ใส่ค่า     | a = $b จะใส่ค่า b ลงตัวแปร a |
| == (Eqality)       | เท่ากับ    | [$a == $b] จะได้ false       |
| != (Not Equality)  | ไม่เท่ากับ | [$a != $b] จะได้ ture                             |

## Relational Operators

| Operator | Purpose                                       | Example           |
| -------- | --------------------------------------------- | ----------------- |
| -eq      | เช็คว่าค่าเท่ากันไหม                          | [$a -eq $b] ไม่จริง |
| -ne      | เช็คว่า่ไม่เท่ากันใช่ไหม                      | [$a -ne $b] จริง    |
| -gt      | เช็คว่าค่าตัวซ้ายมากกว่าตัวขวาไหม             | [$a -gt $b] ไม่จริง |
| -lt      | เช็คว่าค่าตัวซ้ายน้อยกว่าตัวขวาไหม            | [$a -lt $b] จริง    |
| -ge      | เช็คว่าค่าตัวซ้ายมากกว่าหรือเท่ากับตัวขวาไหม  | [$a -ge $b] ไม่จริง |
| -le      | เช็คว่าค่าตัวซ้ายน้อยกว่าตัวขวาหรือเท่ากับไหม | [$a -lt $b] จริง    |


## Boolean Operators

| Operator | Purpose                          | Example                           |
| -------- | -------------------------------- | --------------------------------- |
| !        | สลับ true เป็น false หรือกลับกัน | [! false] จะได้ true              |
| -o       | หรือ (OR)                        | [$a -lt 20 -o $b -gt 100] จริง    |
| -a       | และ (AND)                        | [$a -lt 20 -o $b -gt 100] ไม่จริง | 

## String Operators

| Operator | Purpose                      | Example         |
| -------- | ---------------------------- | --------------- |
| -z       | string size เป็น 0 ใช่ไหม    | [-z $a] ไม่จริง |
| -n       | string size มากกว่า 0 ใช่ไหม | [-n $a] จริง    |
| str      | มีตัวอักษรไหม                | [$a] จริง       |

## File Test Operators
ขอใช้เป็นภาษาอังกฤษ เพราะส่วนใหญ่แปลเป็นไทยแล้วไม่เห็นภาพครับ

| Operator | Purpose                                                                      |
| -------- | ---------------------------------------------------------------------------- |
| -b file  | Checks if file is a block special file                                       |
| -c file  | Checks if file is a character special file                                   |
| -d file  | Checks if file is a directory                                                |
| -f file  | Checks if file is an ordinary file as opposed to a directory or special file |
| -g file  | Checks if file has its set group ID (SGID) bit set                           |
| -k file  | Checks if file has its sticky bit set                                        |
| -p file  | Checks if file is a named pipe                                               |
| -t file  | Checks if file descriptor is open and associated with a terminal             |
| -u file  | Checks if file has its Set User ID (SUID) bit set                            |
| -r file  | Checks if file is readable                                                   |
| -w file  | Checks if file is writable                                                   |
| -x file  | Checks if file is executable                                                 |
| -s file  | Checks if file has size greater than 0                                       |
| =e file  | Checks if file exists                                                        | 


# Shell Loops
## The While Loop
ทำจนกว่าเงื่อนไขจะผิด
มีโครงสร้างพิ้นฐานดังต่อไปนี้

```bash
while command
do
	statement
done
```

ตัวอย่าง

```bash
#!/bin/sh

a=0

while [ $a -lt 10 ] # ถ้า a<10 จะทำจนกว่า a จะมากกว่า 10
do
	echo $a
	a='expr $a + 1'
done
```


## The For Loop
มีโครงสร้างพื้นฐานดังต่อไปนี้

```bash
for var in w1 w2 w3...wN
do
	statement
done
```

ตัวอย่าง
```bash
#!/bin/sh

for var in 0 1 2 3 4 5 6 7 8 9 # แสดง 1-9
do
	echo $var
done
```

## The Until Loop
ทำจนกว่าเงื่อนไขจะเป็นจริง
มีโครงสร้างพิ้นฐานดังต่อไปนี้

```bash
until command
do
	statement
done
```

ตัวอย่าง

```bash
#!/bin/sh

a=0

until [! $a -lt 10 ] # ทำจนกว่า a จะไม่น้อยกว่า 10
do
	echo $a
	a='expr $a + 1'
done

```

## Nested Loop
คือลูปที่ซ้อนกัน
ตัวอย่าง

```bash
#!/bin/sh

a=0

while [ "$a" -lt 10 ] # loop 1
do
	b="$a"
	
	while [ "$b" -ge 0 ] # loop 2
	do
		echo -n "$b " # แสดงโดยไม่เว้นบรรทัด
		b='expr $b - 1'
	done

	echo # เว้นบรรทัด
	a='expr $a + 1'
done

# output
0
1 0
2 1 0
3 2 1 0
4 3 2 1 0
5 4 3 2 1 0
6 5 4 3 2 1 0
7 6 5 4 3 2 1 0
8 7 6 5 4 3 2 1 0
9 8 7 6 5 4 3 2 1 0
```


## Loop Control
ก่อนที่จะรู้จักร Loop control มาทำความรู้จักรกับ infinite loop ก่อน

Infinite Loop คือ loop ที่ทำงานไปเรื่อย ๆ ไม่รู้จบ

```bash
#1/bin/sh

a=10
until [ $a -gt 0 ]
do
	echo $a
	a='expr $a + 1'
done
```

กด crtl+c เพื่อหยุดการทำงานของ loop ทั้งหมด
หรือใช้ break statement เช่น

```bash
#!/bin/sh

a=0

while [ $a -lt 10 ]
do
	echo $a
	if [ $a -eq 5 ]
	then
		break # หยุดลูปต่อเมื่อ a=5
	fi
	a='axpr $a + 1'
done
```

continue statement หยุดการทำงานของ iteration นั้น แต่ยังทำงานในลูปต่อ

```bash
#!/bin/sh

NUMS="1 2 3 4 5 6 7"

for NUM in $NUMS
do
	Q='expr $NUM % 2'
	if [ $Q -eq 0 ]
	then
		echo "Number is an even number!!"
		continue # ถ้าเป็นเลขคู่จะออกจาก iteration ที่ NUM = เลขคู่ แล้วทำต่อ
	fi
	echo "Found odd number"
done	
```

# Shell Function
## Creating Functions
มีโครงสร้างพื้นฐานดังต่อไปนี้

```bash
function name() {
	list of commands
}
```

ตัวอย่าง

```bash
#!/bin/sh

#Define function
Hello(){
	echo "Hello learner"
}

# Invoke Function
Hello
```

## Passing Parameters to Functions

```bash
#!/bin/sh

#Define function
Hello(){
	echo "Hello $1 $2"
}

# Invoke Function
Hello Punyapat Sompoo
```

## Returning Values from Functions

```bash
#!/bin/sh

#Define function
Hello(){
	echo "Hello $1 $2"
	return 10
}

# Invoke Function
Hello Punyapat Sompoo

# Capture value returned previously
ret=$?
echo "Return value is $ret"
```

function ที่สามารถเรียกตัวเองได้คือ "recursive function"

## Nested Functions

```bash
#!/bin/sh

# Define function
number_one(){
	echo "Alpha online...Over"
	number_two
}

number_two(){
	echo "Beta online..Over"
}

number_one
```

## Function Call from Prompt
สามารถบันทึก shell script เหล่านี้ไว้เพื่อเรียกใช้งานผ่าน command promt ได้




# More to Learn
- [Shell Scripting Tutorial | Shell Scripting Crash Course | Linux Certification Training | Edureka](https://www.youtube.com/watch?v=GtovwKDemnI)