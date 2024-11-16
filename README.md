local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("YIMHUM", "Synapse")

local Tab = Window:NewTab("Raid")
local Section = Tab:NewSection("Raid")

function skill()
	local args = {
    [1] = "charge"
}

game:GetService("Players").LocalPlayer.Character.SukunaV3.Remotes.x:FireServer(unpack(args))
	local args = {
    [1] = "release"
}

game:GetService("Players").LocalPlayer.Character.SukunaV3.Remotes.x:FireServer(unpack(args))
wait(1)
local args = {
    [1] = "charge"
}

game:GetService("Players").LocalPlayer.Character.SukunaV3.Remotes.c:FireServer(unpack(args))
	local args = {
    [1] = "release"
}

game:GetService("Players").LocalPlayer.Character.SukunaV3.Remotes.c:FireServer(unpack(args))
wait(1)
local args = {
    [1] = "charge"
}

game:GetService("Players").LocalPlayer.Character.SukunaV3.Remotes.v:FireServer(unpack(args))
	local args = {
    [1] = "release"
}

game:GetService("Players").LocalPlayer.Character.SukunaV3.Remotes.v:FireServer(unpack(args))
wait(1)

end



Section:NewButton("Teleport to raid", "ButtonInfo", function()
    -- ฟังก์ชัน Teleport ตัวละครไปยังตำแหน่งใหม่
function teleportToLocation(player, newPosition)
    -- ตรวจสอบว่าผู้เล่นมีตัวละคร
    if player.Character then
        local character = player.Character
        -- เปลี่ยนตำแหน่งของตัวละคร
        character:SetPrimaryPartCFrame(newPosition)
    end
end

-- ตัวอย่างการใช้ฟังก์ชัน teleport
local player = game.Players.LocalPlayer  -- ผู้เล่นที่ต้องการ teleport
local newPosition = CFrame.new(-35.5150604, 208.882294, 1175.78674, 1, 0, 0, 0, 1, 0, 0, 0, 1)  
teleportToLocation(player, newPosition)

end)
local running = false  -- ตัวแปรตรวจสอบสถานะของ Toggle

-- สร้าง Toggle ที่จะเปิด/ปิดการทำงาน
Section:NewToggle("Autoskill", "Autoskill X C V", function(state)
    if state then
        -- เมื่อเปิด Toggle, ตั้งค่าตัวแปร running เป็น true
        running = true
        -- เริ่มลูปที่ทำงานไปเรื่อย ๆ
        while running do
            skill()
            wait(1)  -- หน่วงเวลา 1 วินาทีระหว่างการทำซ้ำ
        end
    else
        -- เมื่อปิด Toggle, ตั้งค่าตัวแปร running เป็น false เพื่อหยุดลูป
        running = false
        print("Toggle Off")
    end
end)


local Tab = Window:NewTab("main")



