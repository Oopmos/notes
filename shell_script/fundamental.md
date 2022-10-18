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
chmod +r test.sh # read

chmod +w test.sh # write

chmod +x test.sh # excute

chmod 777 test.sh # read + write + excute
```
## man + help