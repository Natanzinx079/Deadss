-- Natan Dead Reails Hub by ChatGPT (feito do zero)
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local UnlockMouse = Instance.new("TextButton")
local UnlockCamera = Instance.new("TextButton")
local RemoveFog = Instance.new("TextButton")
local FullBright = Instance.new("TextButton")
local CloseBtn = Instance.new("TextButton")

ScreenGui.Name = "NatanDeadReails"
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ResetOnSpawn = false

Frame.Name = "MainFrame"
Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Frame.Position = UDim2.new(0.05, 0, 0.3, 0)
Frame.Size = UDim2.new(0, 250, 0, 270)
Frame.Active = true
Frame.Draggable = true

Title.Name = "Title"
Title.Parent = Frame
Title.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
Title.Size = UDim2.new(1, 0, 0, 30)
Title.Font = Enum.Font.GothamBlack
Title.Text = "NATAN DEAD REAILS"
Title.TextColor3 = Color3.fromRGB(255, 0, 0)
Title.TextSize = 18

local function createButton(name, posY, text, callback)
    local btn = Instance.new("TextButton")
    btn.Name = name
    btn.Parent = Frame
    btn.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
    btn.Position = UDim2.new(0, 10, 0, posY)
    btn.Size = UDim2.new(1, -20, 0, 35)
    btn.Font = Enum.Font.Gotham
    btn.Text = text
    btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    btn.TextSize = 14
    btn.MouseButton1Click:Connect(callback)
end

createButton("UnlockMouse", 40, "Unlock Mouse", function()
    local UIS = game:GetService("UserInputService")
    UIS.MouseIconEnabled = true
end)

createButton("UnlockCamera", 85, "Unlock Camera", function()
    local camera = workspace.CurrentCamera
    camera.CameraType = Enum.CameraType.Scriptable
    wait(1)
    camera.CameraType = Enum.CameraType.Custom
end)

createButton("RemoveFog", 130, "Remove Fog", function()
    game:GetService("Lighting").FogEnd = 1000000
end)

createButton("FullBright", 175, "Full Bright", function()
    local lighting = game:GetService("Lighting")
    lighting.Brightness = 2
    lighting.ClockTime = 12
    lighting.FogEnd = 1000000
    lighting.GlobalShadows = false
end)

CloseBtn.Name = "CloseBtn"
CloseBtn.Parent = Frame
CloseBtn.BackgroundColor3 = Color3.fromRGB(60, 0, 0)
CloseBtn.Position = UDim2.new(0, 10, 0, 220)
CloseBtn.Size = UDim2.new(1, -20, 0, 35)
CloseBtn.Font = Enum.Font.GothamBold
CloseBtn.Text = "FECHAR"
CloseBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
CloseBtn.TextSize = 14
CloseBtn.MouseButton1Click:Connect(function()
    ScreenGui:Destroy()
end)
