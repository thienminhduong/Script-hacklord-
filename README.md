loadstring(game:HttpGet(("https://raw.githubusercontent.com/daucobonhi/Ui-Redz-V2/refs/heads/main/UiREDzV2.lua")))()

       local Window = MakeWindow({
         Hub = {
         Title = "minh_duong",
         Animation = "script lỏ"
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
     local Tab2o = MakeTab({Name = "animation hacklord"})
     local Tab3o = MakeTab({Name = "fe pursuer"})
     local Tab4o = MakeTab({Name = "fe noli"})
     local Tab5o = MakeTab({Name = "fe jason"})
     local Tab6o = MakeTab({Name = "fe c00lkidd"})
    local Tab7o = MakeTab({Name = "Krystal dance"})
        local Tab8o = MakeTab({Name = "syntex backdoor 1.2.2"})
         local Tab9o = MakeTab({Name = "syntex backdoor 1.2.0"})
          local Tab10o = MakeTab({Name = "backdoor.exe v6x"})
           local Tab11o = MakeTab({Name = "lalol hub backdoor"})  
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
  AddButton(Tab3o, {
     Name = "fe pursuer",
    Callback = function()
	  loadstring(game:HttpGet("https://gist.githubusercontent.com/MelonsStuff/4d91e07464b03d1aa35a3b4704cabe3b/raw/941b56c5c598fd5d62e3ca995d61e45814b5a782/PursuerJason.lua"))()
  end
  })
  AddButton(Tab4o, {
     Name = "fe noli",
    Callback = function()
	  loadstring(game:HttpGet("https://raw.githubusercontent.com/randomstring0/qwertys/refs/heads/main/qwerty0.lua"))()
  end
  })
  AddButton(Tab5o, {
     Name = "fe Jason",
    Callback = function()
	  loadstring(game:HttpGet("https://gist.githubusercontent.com/MelonsStuff/6203b323781cfb0a7ad35e4e9f60e026/raw/222815c2a4f6ffe38f8ae3965f6b3640c180ab4c/Jason.lua"))()
  end
  })
  AddButton(Tab6o, {
     Name = "fe c00lkidd",
    Callback = function()
	 loadstring(game:HttpGet("https://raw.githubusercontent.com/randomstring0/qwertys/refs/heads/main/qwerty2.lua"))() 
  end
  })
  AddButton(Tab7o, {
     Name = "Krystal dance",
    Callback = function()
	  getgenv().options = { -- SCRIPT OPTIONS
    RagdollGravity = 196.2 -- change to any number above 0 (196.2 is default grav)
}
_G.HideCharacter = true
_G.FlingEnabled = true
_G.TransparentRig = true
_G.ToolFling = false -- false = holding, true = fling
_G.AntiFling = false
_G.CustomHats = false -- Enable or disable custom rig feature (basically old oxide when false)
_G.CH = {
    Torso = {
        Name= "Black",
        TextureId = "14251599953",
        Orientation= CFrame.Angles(math.rad(0),math.rad(0),math.rad(0))
    },

    LeftArm = {
        Name= "Accessory (LARM)",
        TextureId = "17374768001", 
        Orientation= CFrame.Angles(math.rad(0),math.rad(0),math.rad(90))
    },

    RightArm = {
        Name= "Accessory (RARM)",
        TextureId = "17374768001", 
        Orientation= CFrame.Angles(math.rad(0),math.rad(0),math.rad(90))
    },

    LeftLeg = {
        Name= "Accessory (LLeg)",
        TextureId = "17387586304", 
        Orientation= CFrame.Angles(math.rad(0),math.rad(0),math.rad(90))
    },

    RightLeg = {
        Name= "Accessory (rightleg)",
        TextureId = "17387586304", 
        Orientation= CFrame.Angles(math.rad(0),math.rad(0),math.rad(90))
    }
}
loadstring(game:HttpGet("https://raw.githubusercontent.com/Nitro-GT/Oxide/refs/heads/main/genericloadstring"))()
task.wait(.5) -- we give it time to load properly
loadstring(game:HttpGet("https://raw.githubusercontent.com/somethingsimade/KDV3-Fixed/refs/heads/main/KrystalDance3"))()
  end
  })
  AddButton(Tab8o, {
     Name = "syntex backdoor 1.2.2",
    Callback = function()
	loadstring(game:HttpGet('https://raw.githubusercontent.com/etgaby33/syntex_backdoor/refs/heads/main/sb1.2.2.lua'))()  
  end
  AddButton(Tab9o, {
     Name = "syntex backdoor 1.2.0",
    Callback = function()
	 loadstring(game:HttpGet('https://raw.githubusercontent.com/etgaby33/sb1.2.0/refs/heads/main/sb1.2.0lua.txt'))()
  end
  AddButton(Tab10o, {
     Name = "backdoor.exe v6x",
    Callback = function()
	 loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Backdoor-exe-9413"))() 
  end
  AddButton(Tab11o, {
     Name = "lalol hub backdoor",
    Callback = function()
	 loadstring(game:HttpGet('https://raw.githubusercontent.com/Its-LALOL/LALOL-Hub/main/Backdoor-Scanner/script'))()
  end
