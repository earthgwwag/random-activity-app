import tkinter as tk
import random

# ลิสต์กิจกรรม
activities = [
    "วาดรูปแมวลงกระดาษ",
    "เดินเล่นรอบบ้าน 5 นาที",
    "ฟังเพลงโปรด 1 เพลง",
    "เขียน 3 สิ่งที่คุณขอบคุณวันนี้",
    "จัดโต๊ะทำงานให้เรียบร้อย",
    "ลองนั่งสมาธิ 1 นาที",
    "ยืดเส้นยืดสายเบาๆ",
    "เขียนบันทึกสั้นๆ เกี่ยวกับวันของคุณ",
    "เปิดยูทูปดูอะไรสนุกๆ 1 คลิป",
    "หาอะไรเย็นๆ ดื่ม",
    "ทำงานค้าง",
    "ทำงานครูเเสง",
    "มาตากเเอร์ห้องคอมครูเเสง",
    "ฝึกทำอาหาร",
    "ขับรถเล่น",
    "เล่นกีฬา",
    "ออกไปวิ่ง",
    "ออกกำลังกาย",
    "ออกไปปั่นจักรยาน",
    "ฝึกเล่นเครื่องดนตรี",
    "ออกจากบ้านไปหาเพื่อน",
]

# เก็บกิจกรรมที่ยังเหลือ
remaining = activities.copy()
def suggest_activity():
    global remaining
    if not remaining:  # ถ้าหมดแล้วก็รีใหม่
        remaining = activities.copy()
    activity = random.choice(remaining)
    remaining.remove(activity)  # เอาออกจากลิสต์ จะได้ไม่ซ้ำ
    label_result.config(text=activity)
    # GUI
root = tk.Tk()
root.title("แอพสุ่มกิจกรรมเลิกเบื่อ")
root.geometry("400x200")

label_title = tk.Label(root, text="กดปุ่มเพื่อรับกิจกรรมแก้เบื่อ!", font=("Arial", 14))
label_title.pack(pady=10)

button = tk.Button(root, text="สุ่มกิจกรรม!", command=suggest_activity, font=("Arial", 12))
button.pack(pady=10)

label_result = tk.Label(root, text="", font=("Arial", 12), wraplength=350, fg="blue")
label_result.pack(pady=10)

root.mainloop()
print('นาย อดิศักดิ์ ป้องกัน เลขที่14')
