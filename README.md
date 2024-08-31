# DevHub UI Library

ขอแนะนำ DevHub UI Library ซึ่งเป็นไลบรารี่ UI Exploit ของ Roblox ที่สร้างขึ้นเพื่อความสนุกเท่านั้น คุณสามารถปรับเปลี่ยนได้ตามต้องการ และการใช้ไลบรารี่ของเราช่วยเราได้มาก!

## การเริ่มต้น

ในการเริ่มต้น คุณต้องประกาศตัวแปรเพื่อเข้าถึง Library

```lua
local DevHubLibrary = loadstring(game:HttpGet(""))()
```

หากต้องการโหลด UI เพียงเรียกใช้ฟังก์ชัน:

```lua
local window = DevHubLibrary:Load("DevHub", "Default")
```

**อาร์กิวเมนต์ 1: ชื่อ UI ของคุณ (ประเภท: string)**

**อาร์กิวเมนต์ 2: ID รูปภาพ การตั้งค่าเป็น "Default" จะใช้โลโก้ UI Default (ประเภท: string)**

## การนำคุณลักษณะไปใช้

เราจัดเตรียมคุณสมบัติสำเร็จรูปไว้เพื่อความสะดวกของคุณ

### แท็บ

คุณสามารถสร้างแท็บหลายแท็บเพื่อจัดระเบียบฟีเจอร์ของคุณได้

```lua
local tab = DevHubLibrary.newTab("My Tab", "ImageIdHere")
```

**อาร์กิวเมนต์ 1: ชื่อแท็บของคุณ (ชนิด: string)**

**อาร์กิวเมนต์ 2: ID รูปภาพ (ชนิด: string)**

### ปุ่ม

สร้างปุ่มฟังก์ชันได้อย่างง่ายดาย!

```lua
tab.newButton("Button", "Prints Hello!", function()
    print('Hello!')
end)
```

**อาร์กิวเมนต์ 1: ชื่อของปุ่ม (ชนิด: string)**

**อาร์กิวเมนต์ 2: คำอธิบายของปุ่ม (ชนิด: string)**

**อาร์กิวเมนต์ที่ 3: ฟังก์ชันที่จะดำเนินการเมื่อคลิกปุ่ม (ชนิด: function)**

### สลับ

ใช้สวิตช์ที่สามารถเปิดหรือปิดได้

```lua
tab.newToggle("Toggle", "Toggle! (prints the state)", true, function(toggleState)
    if toggleState then
        print("On")
    else
        print("Off")
    end
end)
```

**อาร์กิวเมนต์ 1: ชื่อ (ชนิด: string)**

**อาร์กิวเมนต์ 2: คำอธิบาย (ประเภท: string)**

**อาร์กิวเมนต์ที่ 3: สถานะสลับเริ่มต้น (ชนิด: boolean)**

**อาร์กิวเมนต์ที่ 4: ฟังก์ชันที่จะดำเนินการ (ส่งคืน: bool) (ชนิด: function)**

### อินพุตข้อความ

รับข้อความอินพุตจากผู้ใช้

```lua
tab.newInput("Input", "Prints your input.", function(text)
    print("Entered text: " .. text)
end)
```

**อาร์กิวเมนต์ 1: ชื่อ/ตำแหน่ง (ประเภท: string)**

**อาร์กิวเมนต์ 2: คำอธิบาย (ประเภท: string)**

**อาร์กิวเมนต์ที่ 3: ฟังก์ชันที่จะดำเนินการ (ชนิด: function)**

## เมนูแบบดร็อปดาวน์

สร้างเมนูแบบดรอปดาวน์ได้อย่างง่ายดาย!

```lua
tab.newDropdown("Dropdown", "Select one of these options!", {"water", "dog", "air", "bb", "airplane", "wohhho", "yeay", "delete"}, function(selectedOption)
    print(selectedOption)
end)
```

**อาร์กิวเมนต์ 1: ชื่อ/ตำแหน่ง (ประเภท: string)**

**อาร์กิวเมนต์ 2: คำอธิบาย (ประเภท: string)**

**อาร์กิวเมนต์ 3: ตารางแสดงตัวเลือก (ชนิด: table)**

**อาร์กิวเมนต์ที่ 4: ฟังก์ชันที่จะดำเนินการ ส่งคืนตัวเลือกที่เลือกภายในตาราง (ส่งคืน: สตริง) (ชนิด: function)**

### ปุ่มกำหนดเอง

รับข้อมูลจากผู้ใช้เมื่อคลิกปุ่มเชื่อมต่อแป้นพิมพ์

```lua
tab.newKeybind("Input Key", "Press the key to start; it will be printed out.", function(key)
    print(key)
end)
```

**อาร์กิวเมนต์ 1: ชื่อ/ตำแหน่ง (ประเภท: string)**

**อาร์กิวเมนต์ 2: คำอธิบาย (ประเภท: string)**

**อาร์กิวเมนต์ที่ 3: ฟังก์ชันที่จะดำเนินการ (ส่งคืน: อินพุต) (ชนิด: function)**

### แทบเลื่อน

เพิ่มแถบเลื่อนซึ่งใช้งานได้ดีสำหรับผู้ใช้มือถือด้วย!

```lua
tab.newSlider("Slider", "Epic slider", 1000, false, function(num)
    print(num)
end)
```

**อาร์กิวเมนต์ 1: ชื่อ/ตำแหน่ง (ประเภท: string)**

**อาร์กิวเมนต์ 2: คำอธิบาย (ประเภท: string)**

**อาร์กิวเมนต์ 3: ค่าสูงสุดสำหรับสไลเดอร์ (ชนิด: int)**

**อาร์กิวเมนต์ที่ 4: ตั้งค่าfalseเป็นตอนนี้ (ประเภท: boolean)**

**อาร์กิวเมนต์ 5: ฟังก์ชันที่จะดำเนินการ (ส่งคืน: int) (ชนิด: function)**

## คุณสมบัติ UI ในตัว

นอกจากนี้เรายังมีคุณสมบัติในการสลับ UI เปลี่ยนธีม และอื่นๆ อีกมากมาย!

### สลับ UI

หากต้องการสลับ UI ให้ใช้ดังต่อไปนี้:

```lua
window:Toggle()
```

### เปิด UI

หากต้องการเปิด UI เพียงใช้:

```lua
window:Open()
```

### ปิด UI

หากต้องการปิด UI คุณสามารถใช้:

```lua
window:Close()
```

### ซ่อน UI

หากต้องการซ่อน UI ให้ใช้:

```lua
window:Hide()
```

### แสดง/ยกเลิกการซ่อน UI

เพื่อแสดง UI ให้ใช้:

```lua
window:Show()
```

### ปรับแต่งธีม

คุณสามารถปรับแต่งสีธีมด้วยสีเน้น 2 สี

```lua
local mainColor = Color3.fromRGB(10, 30, 10) -- Customize as you wish; these are in RGB format. (mainColor applies to main colors like background, buttons, etc.)

local secondColor = Color3.fromRGB(50, 50, 10) -- Secondary Color; applies to Toggle when activated and slider background.

window:SetTheme(mainColor, secondColor)
```

**อาร์กิวเมนต์ 1: สีหลัก, พื้นหลัง, สีปุ่ม ฯลฯ (ประเภท: Color3)**

**อาร์กิวเมนต์ที่ 2: สีรอง สลับเมื่อเปิดใช้งาน สีพื้นหลังของแถบเลื่อน (ประเภท: Color3)**

# สงวนสิทธิ์

**ให้นำไปใช้งานได้ฟรีโดยไม่ต้องขออนุญาต**

[MIT License](./LICENSE)

เพลิดเพลินไปกับการใช้ DevHub UI Library! สนุกไปเลย!
