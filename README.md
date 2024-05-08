-- Define GUI
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "Skidded"
ScreenGui.Parent = game.Players.LocalPlayer.PlayerGui

local Frame = Instance.new("Frame")
Frame.Size = UDim2.new(0, 200, 0, 150)
Frame.Position = UDim2.new(0.5, -100, 0.5, -75)
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Frame.BorderSizePixel = 2
Frame.BorderColor3 = Color3.fromRGB(255, 255, 255)
Frame.Parent = ScreenGui

local AimlockButton = Instance.new("TextButton")
AimlockButton.Size = UDim2.new(0, 180, 0, 40)
AimlockButton.Position = UDim2.new(0.5, -90, 0.1, 0)
AimlockButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
AimlockButton.BorderSizePixel = 2
AimlockButton.BorderColor3 = Color3.fromRGB(255, 255, 255)
AimlockButton.Text = "Aimlock: OFF"
AimlockButton.TextColor3 = Color3.fromRGB(255, 255, 255)
AimlockButton.Parent = Frame

local SilentAimButton = Instance.new("TextButton")
SilentAimButton.Size = UDim2.new(0, 180, 0, 40)
SilentAimButton.Position = UDim2.new(0.5, -90, 0.3, 0)
SilentAimButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
SilentAimButton.BorderSizePixel = 2
SilentAimButton.BorderColor3 = Color3.fromRGB(255, 255, 255)
SilentAimButton.Text = "Silent Aim: OFF"
SilentAimButton.TextColor3 = Color3.fromRGB(255, 255, 255)
SilentAimButton.Parent = Frame

local CamlockButton = Instance.new("TextButton")
CamlockButton.Size = UDim2.new(0, 180, 0, 40)
CamlockButton.Position = UDim2.new(0.5, -90, 0.5, 0)
CamlockButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
CamlockButton.BorderSizePixel = 2
CamlockButton.BorderColor3 = Color3.fromRGB(255, 255, 255)
CamlockButton.Text = "Camlock: OFF"
CamlockButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CamlockButton.Parent = Frame

-- Define functions to toggle settings
local function ToggleAimlock()
    getgenv().Aimlock.Enabled = not getgenv().Aimlock.Enabled
    AimlockButton.Text = "Aimlock: " .. (getgenv().Aimlock.Enabled and "ON" or "OFF")
end

local function ToggleSilentAim()
    getgenv().SilentAim.Enabled = not getgenv().SilentAim.Enabled
    SilentAimButton.Text = "Silent Aim: " .. (getgenv().SilentAim.Enabled and "ON" or "OFF")
end

local function ToggleCamlock()
    getgenv().Camlock.Enabled = not getgenv().Camlock.Enabled
    CamlockButton.Text = "Camlock: " .. (getgenv().Camlock.Enabled and "ON" or "OFF")
end

-- Connect buttons to functions
AimlockButton.MouseButton1Click:Connect(ToggleAimlock)
SilentAimButton.MouseButton1Click:Connect(ToggleSilentAim)
CamlockButton.MouseButton1Click:Connect(ToggleCamlock)

-- Load external script
loadstring(game:HttpGet(
