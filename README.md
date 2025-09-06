# Script-hacklord-
loadstring(game:HttpGet(("https://raw.githubusercontent.com/daucobonhi/Ui-Redz-V2/refs/heads/main/UiREDzV2.lua")))()

       local Window = MakeWindow({
         Hub = {
         Title = "minh_duong",
         Animation = "script hacklord"
         },
        Key = {
        KeySystem = false,
        Title = "Key System",
        Description = "",
        KeyLink = "",
        Keys = {"1234"},
        Notifi = {
        Notifications = true,
        CorrectKey = "Running the Script...",
       Incorrectkey = "The key is incorrect",
       CopyKeyLink = "Copied to Clipboard"
      }
    }
  })

       MinimizeButton({
       Image = "http://www.roblox.com/asset/?id=83190276951914",
       Size = {60, 60},
       Color = Color3.fromRGB(10, 10, 10),
       Corner = true,
       Stroke = false,
       StrokeColor = Color3.fromRGB(255, 0, 0)
      })
      
------ Tab
     local Tab1o = MakeTab({Name = "animation hacklord"})
     
------- BUTTON
    
    AddButton(Tab1o, {
     Name = "animation",
    Callback = function()
	  loadstring(game:HttpGet("https://gist.githubusercontent.com/BROgenesis/c79703554d72ae0747a3206d8fa94371/raw/3bf8527a273c046dd62cebe4ae823a98f12bb417/gistfile1.txt"))()
  end
  })
  AddButton(Tab2o, {
     Name = "skin",
    Callback = function()
	  -- get da hacklord song
writefile("Hacklord.mp3", game:HttpGet("https://github.com/ian49972/smth/raw/refs/heads/main/Hacklord.mp3"))

local Players = game:GetService("Players")
local player = Players.LocalPlayer
local Lighting = game:GetService("Lighting")

local UGCs = {
    {74565924591034, "Head", "MASK", CFrame.new(-0.2, 0, 0.5) * CFrame.Angles(0, math.rad(15), 0)},
    {104159695301556, "Head", "CROWN", CFrame.new(0, -0.7, 0)},
    {137773407236137, "Torso", "COFFIN", CFrame.new(0, 0, -1.5)},
    {109671853459724, "Torso", "VEST", CFrame.new(0, 0.5, -1)},
    {75847829270060, "Torso", "CHAINS", CFrame.new(0, 0, -1)},
    {121290673270759, "Torso", "SWORD", CFrame.new(0, 0.4, -0.6)},
    {84452359312672, "Torso", "VEST2", CFrame.new(0, 0, 0)},
    {138934488961238, "Right Arm", "RIGHT ARM", CFrame.new(0, 0, 0)},
    {110693960146571, "Left Arm", "LEFT ARM", CFrame.new(0, 0, 0)},
}

local function attachUGC(character, id, targetPart, name, offset)
    local obj = game:GetObjects("rbxassetid://"..id)[1]
    if not obj then return end
    obj.Name = name
    obj.Parent = character

    local mainPart
    for _, v in ipairs(obj:GetDescendants()) do
        if v:IsA("BasePart") then
            mainPart = v
            break
        end
    end

    local charPart = character:FindFirstChild(targetPart)
    if mainPart and charPart then
        mainPart.CFrame = charPart.CFrame * offset
        local weld = Instance.new("Weld")
        weld.Part0 = charPart
        weld.Part1 = mainPart
        weld.C0 = CFrame.new()
        weld.C1 = offset
        weld.Parent = charPart
    end
end

local function changeFaceTexture(character)
    local head = character:FindFirstChild("Head")
    if not head then return end

    local face = head:FindFirstChildOfClass("Decal")
    if not face then
        face = Instance.new("Decal")
        face.Name = "face"
        face.Face = Enum.NormalId.Front
        face.Parent = head
    end

    face.Texture = "rbxassetid://17104347268"
end

local function runIntro(character)
    local sound = Instance.new("Sound")
    sound.SoundId = getcustomasset("Hacklord.mp3")
    sound.Volume = 1
    sound.Looped = true
    sound.Parent = workspace
    sound:Play()

    Lighting.TimeOfDay = "02:00:00"
    Lighting.Brightness = 0
    Lighting.ClockTime = 2
    Lighting.FogEnd = 10000
    Lighting.FogStart = 0
    Lighting.FogColor = Color3.new(0, 0, 0)
    Lighting.Ambient = Color3.new(0, 0, 0)
    Lighting.OutdoorAmbient = Color3.new(0, 0, 0)
    Lighting.GlobalShadows = false
    Lighting.EnvironmentDiffuseScale = 0
    Lighting.EnvironmentSpecularScale = 0

    task.wait(21)

    Lighting.TimeOfDay = "14:00:00"
    Lighting.Brightness = 2
    Lighting.ClockTime = 14
    Lighting.FogEnd = 100000
    Lighting.FogStart = 0
    Lighting.FogColor = Color3.new(1, 1, 1)
    Lighting.Ambient = Color3.new(1, 1, 1)
    Lighting.OutdoorAmbient = Color3.new(1, 1, 1)
    Lighting.GlobalShadows = true
    Lighting.EnvironmentDiffuseScale = 1
    Lighting.EnvironmentSpecularScale = 1

    changeFaceTexture(character)

    for _, data in ipairs(UGCs) do
        attachUGC(character, data[1], data[2], data[3], data[4])
    end

    return sound
end

local function setupCharacter(char)
    local music = runIntro(char)

    local humanoid = char:WaitForChild("Humanoid")
    humanoid.Died:Connect(function()
        if music and music.IsPlaying then
            music:Stop()
        end
    end)
end

if player.Character then
    setupCharacter(player.Character)
end

player.CharacterAdded:Connect(function(char)
    setupCharacter(char)
end)
  end
  })
