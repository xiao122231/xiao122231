local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Window = OrionLib:MakeWindow({Name = "灾难蛋的脚本(内测版本)|Stands awakening", HidePremium = false, SaveConfig = true, ConfigFolder = "SAconfig"})

--Values
_G.AutoTimeStop = true
_G.AutoBlock = true
_G.InfJump = true
_G.AutoRoka = true
_G.AutoArrow = true
_G.InfDamage = true
_G.AutoClone = true
_G.Menacing = true











--Functions

function AutoTimeStop()
while _G.AutoTimeStop == true do
    local args = {
        [1] = 114514,
        [2] = "thwoh"
    }
    
    game:GetService("ReplicatedStorage").Main.Timestop:FireServer(unpack(args))
    wait(.0001)
    end
end

function AutoBlock()
    while _G.AutoBlock == true do
        local args = {
            [1] = "Alternate",
            [2] = "Block"
        }
        
        game:GetService("ReplicatedStorage").Main.Input:FireServer(unpack(args))
        wait(.0001)
    end
end

function InfJump()
    while _G.InfJump == true do


        game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
wait(.000000001)
end
end

function AutoRoka()
   while _G.AutoRoka == true do
   game:GetService("ReplicatedStorage").ItemEvents.Roka:FireServer()
wait(.0001)
end
end

function AutoArrow()
while _G.AutoArrow == true do
game:GetService("ReplicatedStorage").ItemEvents.Arrow:FireServer()
wait(.0001)
end
end

function InfDamage()
while _G.InfDamage == true do
local args = {
    [1] = "Alternate",
    [2] = "RTZ",
    [3] = true
}

game:GetService("ReplicatedStorage").Main.Input:FireServer(unpack(args))
wait(.0001)
end
end

function AutoClone()
while _G.AutoClone == true do
local args = {
    [1] = "Alternate",
    [2] = "Clone"
}

game:GetService("ReplicatedStorage").Main.Input:FireServer(unpack(args))
wait(0.000001)
end
end

function Menacing()
while _G.Menacing == true do
local args = {
    [1] = true
}

game:GetService("ReplicatedStorage").Main.Menacing:FireServer(unpack(args))
wait(0.01)
end
end









--Tabs
local FirstTab = Window:MakeTab({
	Name = "功能类",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})
local Section = FirstTab:AddSection({
	Name = "时停类角色需要"
})
FirstTab:AddButton({
	Name = "时停",
	Callback = function()
     local args = {
    [1] = 114514,
    [2] = "thwoh"
}

game:GetService("ReplicatedStorage").Main.Timestop:FireServer(unpack(args)) 		
  	end    
})


FirstTab:AddToggle({
	Name = "自动时停",
	Default = false,
	Callback = function(Value)
		_G.AutoTimeStop = Value
        AutoTimeStop()
	end    
})

local Section = FirstTab:AddSection({
	Name = "需要黄镇类"
})

FirstTab:AddToggle({
	Name = "无限反伤",
	Default = false,
	Callback = function(Value)
		_G.InfDamage = Value
        InfDamage()
	end    
})
















local Section = FirstTab:AddSection({
	Name = "可防御替身可用"
})

FirstTab:AddToggle({
	Name = "减伤",
	Default = false,
	Callback = function(Value)
		_G.AutoBlock = Value
        AutoBlock()
	end    
})

local Tab2 = Window:MakeTab({
	Name = "玩家类",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

Tab2:AddToggle({
	Name = "向上飞",
	Default = false,
	Callback = function(Value)
	    _G.InfJump = Value
	    InfJump()
	end    
})


local Tab3 = Window:MakeTab({
	Name = "自动类",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})




local Section = FirstTab:AddSection({
	Name = "需要D4C的功能"
})



FirstTab:AddToggle({
	Name = "D4C无限克隆体",
	Default = false,
	Callback = function(Value)
	    _G.AutoClone = Value
	    AutoClone()
	end    
})

local Tab4 = Window:MakeTab({
	Name = "娱乐类",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

Tab4:AddToggle({
	Name = "身上冒特效",
	Default = false,
	Callback = function(Value)
	    _G.Menacing = Value
	    Menacing()
	end    
})








Tab3:AddToggle({
	Name = "自动吃果实",
	Default = false,
	Callback = function(Value)
	    _G.AutoRoka = Value
	    AutoRoka()
	end    
})

Tab3:AddToggle({
	Name = "自动扎箭",
	Default = false,
	Callback = function(Value)
	    _G.AutoArrow = Value
	    AutoArrow()
	end    
})
















OrionLib:Init()
