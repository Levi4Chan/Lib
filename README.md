# [Mercury](Mercury%20Lib/source.lua)

```lua
local Mercury = loadstring(game:HttpGet("https://raw.githubusercontent.com/deeeity/mercury-lib/master/src.lua"))()
```
```lua
local GUI = Mercury:Create{
    Name = "Mercury",
    Size = UDim2.fromOffset(600, 400),
    Theme = self.Themes.Dark,
    Link = "https://github.com/deeeity/mercury-lib"
}
```
```lua
local Tab = GUI:Tab{
	Name = "New Tab",
	Icon = "rbxassetid://8569322835"
}
```
```lua
Tab:Button{
	Name = "Button",
	Description = nil,
	Callback = function() end
}
```
```lua
Tab:Toggle{
	Name = "Toggle",
	StartingState = false,
	Description = nil,
	Callback = function(state) end
}
```
```lua
Tab:Dropdown{
	Name = "Dropdown",
	StartingText = "Select...",
	Description = nil,
	Items = {},
	Callback = function(item) return end
}
```
```lua
Tab:Slider{
	Name = "Slider",
	Default = 50,
	Min = 0,
	Max = 100,
	Callback = function() end
}
```
```lua
Tab:Keybind{
	Name = "Keybind",
	Keybind = nil,
	Description = nil
}
```
```lua
GUI:Prompt{
	Followup = false,
	Title = "Prompt",
	Text = "Prompts are cool",
	Buttons = {
		ok = function()
			return true
		end
		no = function()
			return false
		end
	}
}
```
```lua
GUI:Notification{
	Title = "Alert",
	Text = "You shall bump the thread on V3rmillion!",
	Duration = 3,
	Callback = function() end
}
```
```lua
GUI:ColorPicker{
	Style = Library.ColorPickerStyles.Legacy,
	Callback = function(color) end
}
```
```lua
GUI:Credit{
	Name = "Creditor's name",
	Description = "Helped with the script",
	V3rm = "link/name",
	Discord = "helo#1234"
}
```

# [Bracket V3](BracketV3/BracketV3%20Lib.lua)

```lua
local Config = {
    WindowName = "Example Library",
	Color = Color3.fromRGB(255,128,64),
	Keybind = Enum.KeyCode.RightBracket
}

local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/Jaaaaay2/Lib/main/BracketV3/BracketV3%20Lib.lua"))()
local Window = Library:CreateWindow(Config, game:GetService("CoreGui"))

local Tab1 = Window:CreateTab("Example")
local Tab2 = Window:CreateTab("UI Settings")

local Section1 = Tab1:CreateSection("First Section")
local Section2 = Tab1:CreateSection("Second Section")
local Section3 = Tab2:CreateSection("Menu")
local Section4 = Tab2:CreateSection("Background")

local Label1 = Section1:CreateLabel("Label 1")
Label1:UpdateText("lol")
-------------
local Button1 = Section1:CreateButton("Button 1", function()
	print("Click Button 1")
end)
Button1:AddToolTip("Button 1 ToolTip")
-------------
local Toggle1 = Section1:CreateToggle("Toggle 1", nil, function(State)
	print(State)
end)
Toggle1:AddToolTip("Toggle 1 ToolTip")
Toggle1:CreateKeybind("Y", function(Key)
	print(Key)
end)

local TextBox1 = Section1:CreateTextBox("TextBox 1", "Only numbers", true, function(Value)
	print(Value)
end)
TextBox1:AddToolTip("Yes only numbers")
TextBox1:SetValue("new value here")
Section1:CreateTextBox("TextBox 1\nMultiline", "numbers and letters", false, function(String)
	print(String)
end)
-------------
local Slider1 = Section1:CreateSlider("Slider 1", 0,100,nil,true, function(Value)
	print(Value)
end)
Slider1:AddToolTip("Slider 1 ToolTip")
Slider1:SetValue(50)
-------------
local Dropdown1 = Section1:CreateDropdown("Dropdown 1", {"Option 1","Option 2","Option 3"}, function(String)
	print(String)
end)
Dropdown1:AddToolTip("Dropdown 1 ToolTip")
Dropdown1:SetOption("Option 1")
-------------
local Colorpicker1 = Section1:CreateColorpicker("Colorpicker 1", function(Color)
	print(Color)
end)
Colorpicker1:AddToolTip("Colorpicker 1 ToolTip")
Colorpicker1:UpdateColor(Color3.fromRGB(255,0,0))
-------------
Section2:CreateLabel("Label 2\nMultiline")
-------------
local Button2 = Section2:CreateButton("Button 2\nMultiline", function()
	print("Click Button 2")
end)
Button2:AddToolTip("Button 2 ToolTip\nMultiline")
-------------
local Toggle2 = Section2:CreateToggle("Toggle 2\nMultiline", nil, function(State)
	print(State)
end)
Toggle2:AddToolTip("Toggle 2 ToolTip\nMultiline")
Toggle2:CreateKeybind("U", function(Key)
	print(Key)
end)
-------------
local Slider2 = Section2:CreateSlider("Slider 2\nMultiline", 0,100,nil,false, function(Value)
	print(Value)
end)
Slider2:AddToolTip("Slider 2 ToolTip\nMultiline")
Slider2:SetValue(25)
-------------
local Dropdown2 = Section2:CreateDropdown("Dropdown 2\nMultiline", {"Option 4","Option 5","Option 6"}, function(String)
	print(String)
end)
Dropdown2:AddToolTip("Dropdown 2 ToolTip")
Dropdown2:SetOption("Option 6")
-------------
local Colorpicker2 = Section2:CreateColorpicker("Colorpicker 2\nMultiline", function(Color)
	print(Color)
end)
Colorpicker2:AddToolTip("Colorpicker 2 ToolTip")
Colorpicker2:UpdateColor(Color3.fromRGB(0,0,255))
-------------
local Toggle3 = Section3:CreateToggle("UI Toggle", nil, function(State)
	Window:Toggle(State)
end)
Toggle3:CreateKeybind(tostring(Config.Keybind):gsub("Enum.KeyCode.", ""), function(Key)
	Config.Keybind = Enum.KeyCode[Key]
end)
Toggle3:SetState(true)

local Colorpicker3 = Section3:CreateColorpicker("UI Color", function(Color)
	Window:ChangeColor(Color)
end)
Colorpicker3:UpdateColor(Config.Color)

-- credits to jan for patterns
local Dropdown3 = Section4:CreateDropdown("Image", {"Default","Hearts","Abstract","Hexagon","Circles","Lace With Flowers","Floral"}, function(Name)
	if Name == "Default" then
		Window:SetBackground("2151741365")
	elseif Name == "Hearts" then
		Window:SetBackground("6073763717")
	elseif Name == "Abstract" then
		Window:SetBackground("6073743871")
	elseif Name == "Hexagon" then
		Window:SetBackground("6073628839")
	elseif Name == "Circles" then
		Window:SetBackground("6071579801")
	elseif Name == "Lace With Flowers" then
		Window:SetBackground("6071575925")
	elseif Name == "Floral" then
		Window:SetBackground("5553946656")
	end
end)
Dropdown3:SetOption("Default")

local Colorpicker4 = Section4:CreateColorpicker("Color", function(Color)
	Window:SetBackgroundColor(Color)
end)
Colorpicker4:UpdateColor(Color3.new(1,1,1))

local Slider3 = Section4:CreateSlider("Transparency",0,1,nil,false, function(Value)
	Window:SetBackgroundTransparency(Value)
end)
Slider3:SetValue(0)

local Slider4 = Section4:CreateSlider("Tile Scale",0,1,nil,false, function(Value)
	Window:SetTileScale(Value)
end)
Slider4:SetValue(0.5)

```

# [IreXion](IreXion%20UI/Source.lua)

```lua
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/IreXion-UI-Library/main/IreXion%20UI%20Library"))()

local Gui = Library:AddGui({
	Title = {"IreXion", "UI Library"},
	ThemeColor = Color3.fromRGB(0, 255, 0),
	ToggleKey = Enum.KeyCode.RightShift,
})

local Tab = Gui:AddTab("Test Tab")

local Category = Tab:AddCategory("Category")

local Button = Category:AddButton("Button", function()
	print("Button Pressed")
end)

local Toggle = Category:AddToggle("Toggle", false, function(toggle)
	print(toggle)
end)

local Box = Category:AddBox("Box", function(str)
	print(str)
end)

local Label = Category:AddLabel("Label")

local DualLabel = Category:AddDualLabel({"Label1", "Label2"})

local Slider = Category:AddSlider("Slider", 1, 100, 50, function(val)
	print("Slider Value:", val)
end)

local Dropdown = Category:AddDropdown("Dropdown", {
	"Item 1",
	"Item 2",
	"Item 3",
	"Item 4",
	"Item 5",
	"Item 6",
	"Item 7",
	"Item 8",
	"Item 9",
	"Item 10",
}, function(name)
	print(name)
end)

local Bind = Category:AddBind("Bind", Gui.ToggleKey, function()
	print("Toggled GUI")
end)

Library:Notify("Thank you for checking out IreXion UI Library.", function(bool)
	print("User clicked", bool and "yes" or "no")
end)

```
