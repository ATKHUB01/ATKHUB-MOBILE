
local DiscordLib = loadstring(game:HttpGet"https://raw.githubusercontent.com/dawid-scripts/UI-Libs/main/discord%20lib.txt")()



local win = DiscordLib:Window("ATK HUB | BLOX FRUIT 17 PT.2")




local serv = win:Server("ATK HUB", "http://www.roblox.com/asset/?id=9059073262")

local main = serv:Channel("Main")

local stats = serv:Channel("Stats")

local island = serv:Channel("Island")

local shop = serv:Channel("Shop")

local fake = serv:Channel("Fake")

local song = serv:Channel("Song")

local raid = serv:Channel("Raid")

local msic = serv:Channel("Msic")

local settings = serv:Channel("Settings")



-- Auto Farm



main:Label("SetSpawn")



_G.SetSpawnPoint = true -- true false

main:Toggle("SetSpawnPoint",_G.SetSpawnPoint, function(value)

   _G.SetSpawnPoint = value

      while _G.SetSpawnPoint do wait()

         local A_1 = "SetSpawnPoint"

         local Event = game:GetService("ReplicatedStorage").Remotes["CommF_"]

         Event:InvokeServer(A_1)

      end

end)



main:Seperator()



main:Label("Farm")



local Weaponlist = {}

local Weapon = nil



for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do

    table.insert(Weaponlist,v.Name)

end



_G.Farm = false -- true false

main:Toggle("Auto Farm Lv.700",_G.Farm, function(value)

	_G.Farm = value

end)



local placeId = game.PlaceId

if placeId == 2753915549 then

	world1 = true

elseif placeId == 4442272183 then

	world2 = true

elseif placeId == 7449423635 then

	world3 = true

end



function toposQ(Para1)

    Distance = (Para1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude

    if Distance < 10 then

        Speed = 10000

    elseif Distance < 150 then

        Speed = 5000

    elseif Distance < 250 then

        Speed = 3500

    elseif Distance < 500 then

        Speed = 400

    elseif Distance < 1000 then

        Speed = 350

    elseif Distance >= 1000 then

        Speed = 200

    end

    game:GetService("TweenService"):Create(

        game.Players.LocalPlayer.Character.HumanoidRootPart,

        TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),

        {CFrame = Para1}

    ):Play()

end



function Lv()

    local lv = game:GetService("Players").LocalPlayer.Data.Level.Value

    

    if lv == 1 or lv <= 9 then

        CFQ = CFrame.new(1058.466796875, 16.362747192383, 1548.1558837891)    

        NameQ = "BanditQuest1"

        LevelQ = 1

        Mon = "Bandit [Lv. 5]"

    elseif lv == 9 or lv <= 15 then

        CFQ = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)    

        NameQ = "JungleQuest"

        LevelQ = 1

        Mon = "Monkey [Lv. 14]"

    elseif lv == 15 or lv <= 30 then

        CFQ = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)    

        NameQ = "JungleQuest"

        LevelQ = 2

        Mon = "Gorilla [Lv. 20]"

    elseif lv == 30 or lv <= 40 then

        CFQ = CFrame.new(-1140.515869140625, 4.777853488922119, 3830.275146484375)    

        NameQ = "BuggyQuest1"

        LevelQ = 1

        Mon = "Pirate [Lv. 35]"

    elseif lv == 40 or lv <= 60 then

        CFQ = CFrame.new(-1140.515869140625, 4.777853488922119, 3830.275146484375)

        NameQ = "BuggyQuest1"

        LevelQ = 2

        Mon = "Brute [Lv. 45]"

    elseif lv == 60 or lv <= 75 then

        CFQ = CFrame.new(894.5579223632812, 6.464265823364258, 4390.8271484375)

        NameQ = "DesertQuest"

        LevelQ = 1

        Mon = "Desert Bandit [Lv. 60]"

    elseif lv == 75 or lv <= 90 then

        CFQ = CFrame.new(894.5579223632812, 6.464265823364258, 4390.8271484375)

        NameQ = "DesertQuest"

        LevelQ = 2

        Mon = "Desert Officer [Lv. 70]"

    elseif lv == 90 or lv <= 100 then

        CFQ = CFrame.new(1388.5831298828125, 87.29856872558594, -1297.880615234375)

        NameQ = "SnowQuest"

        LevelQ = 1

        Mon = "Snow Bandit [Lv. 90]"

    elseif lv == 100 or lv <= 120 then

        CFQ = CFrame.new(1388.5831298828125, 87.29856872558594, -1297.880615234375)

        NameQ = "SnowQuest"

        LevelQ = 2

        Mon = "Snowman [Lv. 100]"

    elseif lv == 120 or lv <= 150 then

        CFQ = CFrame.new(-5037.86328125, 28.67783546447754, 4325.15625)

        NameQ = "MarineQuest2"

        LevelQ = 1

        Mon = "Chief Petty Officer [Lv. 120]"

    elseif lv == 150 or lv <= 175 then

        CFQ = CFrame.new(-4840.25634765625, 717.6951293945312, -2620.5537109375)

        NameQ = "SkyQuest"

        LevelQ = 1

        Mon = "Sky Bandit [Lv. 150]"

    elseif lv == 175 or lv <= 225 then

        CFQ = CFrame.new(-4840.25634765625, 717.6951293945312, -2620.5537109375)

        NameQ = "SkyQuest"

        LevelQ = 2

        Mon = "Dark Master [Lv. 175]"

    elseif lv == 225 or lv <= 275 then

        CFQ = CFrame.new(-1577.24853515625, 7.415140628814697, -2985.498046875)

        NameQ = "ColosseumQuest"

        LevelQ = 1

        Mon = "Toga Warrior [Lv. 225]"

    elseif lv == 275 or lv <= 300 then

        CFQ = CFrame.new(-1577.24853515625, 7.415140628814697, -2985.498046875)

        NameQ = "ColosseumQuest"

        LevelQ = 2

        Mon = "Gladiator [Lv. 275]"

    elseif lv == 300 or lv <= 330 then

       CFQ = CFrame.new(-5314.46728515625, 12.745513916015625, 8515.9384765625)

       NameQ = "MagmaQuest"

       LevelQ = 1

       Mon = "Military Soldier [Lv. 300]"

    elseif lv == 330 or lv <= 375 then

       CFQ = CFrame.new(-5314.46728515625, 12.745513916015625, 8515.9384765625)

       NameQ = "MagmaQuest"

       LevelQ = 2

       Mon = "Military Spy [Lv. 330]"

    elseif lv == 375 or lv <= 400 then

       CFQ = CFrame.new(61121.96875, 18.4974365234375, 1565.8970947265625)

       NameQ = "FishmanQuest"

       LevelQ = 1

       Mon = "Fishman Warrior [Lv. 375]"

    elseif lv == 400 or lv <= 450 then

       CFQ = CFrame.new(61121.96875, 18.4974365234375, 1565.8970947265625)

       NameQ = "FishmanQuest"

       LevelQ = 2

       Mon = "Fishman Commando [Lv. 400]"

    elseif lv == 450 or lv <= 475 then

       CFQ = CFrame.new(-4721.51318359375, 845.3027954101562, -1951.3292236328125)

       NameQ = "SkyExp1Quest"

       LevelQ = 1

       Mon = "God's Guard [Lv. 450]"

    elseif lv == 475 or lv <= 525 then

       CFQ = CFrame.new(-7860.27685546875, 5545.517578125, -380.9004211425781)

       NameQ = "SkyExp1Quest"

       LevelQ = 1

       Mon = "Shanda [Lv. 475]"

    elseif lv == 525 or lv <= 550 then

       CFQ = CFrame.new(-7905.2568359375, 5635.98828125, -1411.6693115234375)

       NameQ = "SkyExp2Quest"

       LevelQ = 1

       Mon = "Royal Squad [Lv. 525]"

    elseif lv == 550 or lv <= 625 then

       CFQ = CFrame.new(-7905.2568359375, 5635.98828125, -1411.6693115234375)

       NameQ = "SkyExp2Quest"

       LevelQ = 2

       Mon = "Royal Soldier [Lv. 550]"

    elseif lv == 625 or lv <= 650 then

       CFQ = CFrame.new(5257.97509765625, 38.52693176269531, 4049.527587890625)

       NameQ = "Galley Pirate [Lv. 625]"

       LevelQ = 1

       Mon = "FountainQuest"

    elseif lv == 650 or lv <= 700 then

       CFQ = CFrame.new(5257.97509765625, 38.52693176269531, 4049.527587890625)

       NameQ = "FountainQuest"

       LevelQ = 2

       Mon = "Galley Captain [Lv. 650]"

    elseif lv == 700 or lv <= 2201 then

       CFQ = CFrame.new(-426.756439, 72.9963226, 1837.29504, 0.222316682, -4.21167279e-08, 0.974974513, -3.76689187e-08, 1, 5.17871541e-08, -0.974974513, -4.82393823e-08, 0.222316682)

       NameQ = "Area1Quest"

       LevelQ = 1

       Mon = "Raider [Lv. 700]"

    end

end



spawn(function()

    while wait() do

        pcall(function()

            if _G.Farm then

                if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then

                    Lv()

                    toposQ(CFQ)

                     if (CFQ.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5 then

                    wait(1.5)

                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQ,LevelQ)

                end

                elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then    

                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do

                        if v.Name == Mon and v.Humanoid.Health > 0 then

                        repeat wait()

                            game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)

                            toposQ(v.HumanoidRootPart.CFrame*CFrame.new(20,20,0)) 

                            v.HumanoidRootPart.Size = Vector3.new(60,60,60)

                            v.HumanoidRootPart.CanCollide = false 

                            game:GetService("VirtualUser"):CaptureController()

            game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 670),workspace.CurrentCamera.CFrame)

                        until v.Humanoid.Health <= 0 or _G.Farm == false

                        end

                    end

                end

            end

        end)

    end

end)



spawn(function()

    while wait() do 

    pcall(function()

            if _G.Farm then

                local Xd = Instance.new("Part")

                Xd.Name = "xd"

                Xd.Parent = game.Workspace

                Xd.Anchored = true

                Xd.Transparency = 0

                Xd.Color = Color3.fromRGB(0, 255, 255)

                Xd.Size = Vector3.new(15,0.5,15)

                Xd.Material = "Neon"



                if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-game.Workspace["xd"].Position).Magnitude > 5 then

                    game.Workspace["xd"].CFrame = CFrame.new(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.X,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Y-1.5,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Z)

                end





            else

                if game:GetService("Workspace").xd then

                    game:GetService("Workspace").xd:Destroy()

                end

            end





    end)

    end

end)



spawn(function()

while wait() do

if _G.Farm then

pcall(function()

game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))

end)

end

end

end)



local SelectToolWeapona = main:Dropdown("Select Weapon",Weaponlist, function(value)

	Weapon = value

end)



main:Button("Reset Weapon", function()

SelectToolWeapona:Clear()

    Wapon = {}

    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  

        if v:IsA("Tool") then

            SelectToolWeapona:Add(v.Name)

        end

    end

    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  

        if v:IsA("Tool") then

            SelectToolWeapona:Add(v.Name)

        end

    end

end)



-- Stats



stats:Seperator()



stats:Label("Auto Stats")



_G.Melee = false -- true false

stats:Toggle("Melee",_G.Melee, function(value)

   _G.Melee = value

      while _G.Melee do wait() 

         local A_1 = "AddPoint"

         local A_2 = "Melee"

         local A_3 = 1

         local Event = game:GetService("ReplicatedStorage").Remotes["CommF_"]

         Event:InvokeServer(A_1, A_2, A_3)

      end

end)



_G.Defense = false -- true false

stats:Toggle("Defense",_G.Defense, function(value)

   _G.Defense = value

      while _G.Defense do wait() 

         local A_1 = "AddPoint"

         local A_2 = "Defense"

         local A_3 = 1

         local Event = game:GetService("ReplicatedStorage").Remotes["CommF_"]

         Event:InvokeServer(A_1, A_2, A_3)

      end

end)



_G.Sword = false -- true false

stats:Toggle("Sword",_G.Sword, function(value)

   _G.Sword = value

      while _G.Sword do wait() 

         local A_1 = "AddPoint"

         local A_2 = "Sword"

         local A_3 = 1

         local Event = game:GetService("ReplicatedStorage").Remo
