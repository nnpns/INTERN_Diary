# 📅 Day 48 - วันที่ 48 ของการฝึกงาน
**วันที่:** 21 สิงหาคม 2025  
**สถานที่ฝึกงาน:** บริษัท TECH CARE SOLUTION Co.Ltd,  
**ตำแหน่ง:** นักพัฒนาซอฟต์แวร์ฝึกหัด


---

## 📝 สิ่งที่ได้ทำในวันนี้
- อัพเดตงานที่ได้รับมอบหมายและแก้ไขต่อ
- ได้รับมอบหมายให้ทำการดึงรูปโปรไฟล์ของ User มาใช้แทน Icon.person หน้า Backlog ตรงจุดที่แสดงผู้รับผิดชอบงาน


```


```

---

## 🎯 สิ่งที่เรียนรู้ในวันนี้ 
- 




---

## 🤔 ปัญหาที่พบวันนี้
- การดึงรูปของ User มาใช้ แล้วรูปไม่แสดง
- โค้ดชุดนี้มีปัญหาคือ เมื่อมีการเปิดแอปรูปภาพจะหาย ต้องทำการเข้าไปเลือกผู้รับผิดชอบใหม่และอัพเดตอีกครั้ง รูปถึงจะกลับมาแสดง 

```
Widget _buildAssigneeInfo(TaskModel task) {
  final userProfileImage = ref.watch(userProfileImageProvider(task.assignedTo?.id));
  final hasLocalImage = task.assignedTo?.image != null && task.assignedTo!.image!.isNotEmpty;

  return Row(
    mainAxisSize: MainAxisSize.min,
    children: [
      Tooltip(
        message: task.assignedTo?.name ?? 'ไม่มีผู้รับผิดชอบ',
        child: CircleAvatar(
          radius: 12,
          backgroundColor: Colors.grey[300],
          backgroundImage: userProfileImage.maybeWhen(
            data: (url) => url?.isNotEmpty == true ? NetworkImage(url!) : null,
            orElse: () => null,
          ) ?? (hasLocalImage ? NetworkImage(task.assignedTo!.image!) : null),
          child: userProfileImage.maybeWhen(
            data: (url) => (url?.isNotEmpty == true || hasLocalImage) ? null : const Icon(Icons.person, size: 16, color: Colors.black),
            orElse: () => hasLocalImage ? null : const Icon(Icons.person, size: 16, color: Colors.black),
          ),
        ),
      ),
    ],
  );
}

```


---

## ✅ วิธีแก้ไข
- 


---

## 💡 สิ่งที่อยากพัฒนาต่อ
- ฝึกเขียนโปรแกรมให้มากขึ้น
- 



---

## 😄 ความรู้สึกวันนี้
- 
