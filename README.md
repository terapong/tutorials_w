# tutorials_w
# cd pico-example
# mkdir build
# cd build
# cmake -DPICO_BOARD=pico_w ..
# cd pico_w/wifi/blink/
# make -j4

cmake -DPICO_BOARD=pico_w ..
cmake .. -DPICO_BOARD=pico_w ..
make

sudo apt install minicom
sudo minicom -b 115200 -o -D /dev/ttyACM0


target_include_directories(tutorial_w PRIVATE ${CMAKE_CURRENT_LIST_DIR}) 
ไอ้นี้อยู่ี่ไหน หว่ะ ${CMAKE_CURRENT_LIST_DIR}

ในขณะที่ CMake ประมวลผลไฟล์รายการในโครงการของคุณ ตัวแปรนี้จะถูกตั้งค่าเป็นไดเร็กทอรีที่มีไฟล์รายการที่กำลังประมวลผลอยู่ (CMAKE_CURRENT_LIST_FILE) อยู่เสมอ ค่านี้มีขอบเขตแบบไดนามิก เมื่อ CMake เริ่มประมวลผลคำสั่งในไฟล์ต้นฉบับ จะตั้งค่าตัวแปรนี้ไปยังไดเร็กทอรีที่ไฟล์นี้ตั้งอยู่ เมื่อ CMake เสร็จสิ้นการประมวลผลคำสั่งจากไฟล์ มันจะคืนค่าค่าก่อนหน้า ดังนั้นค่าของตัวแปรภายในมาโครหรือฟังก์ชันจึงเป็นไดเร็กทอรีของไฟล์ที่เรียกใช้รายการที่อยู่ด้านล่างสุดบน call stack ไม่ใช่ไดเร็กทอรีของไฟล์ที่มีมาโครหรือคำจำกัดความของฟังก์ชัน
