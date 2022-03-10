_G.FarmLevel = false

function CheckLevel()
    local MyLevel = game.Players.LocalPlayer.Data.Level.Value
        
    if MyLevel == 1 or MyLevel <= 9000 then
        Ms = "Bandit [Lv. 5]"
        NameMon = "Bandit"
        NameQuest = "BanditQuest1"
        LevelQuest = 1
        CFrameQuest = CFrame.new(1061.11, 16.3627, 1549.23)
    end
end
function toposQ(Para1)
    Distance = (Para1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude

    if Distance < 150 then
        Speed = 3800
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

spawn(function()
    while task.wait() do
        pcall(function()
            if _G.FarmLevel then
                CheckLevel()
                if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                    Magnet = false
                    workspace.Gravity = 196.19999694824
                    toposQ(CFrameQuest)
                    if (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5 then
                    wait(1.7)
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQuest,LevelQuest)
                    end
                elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                     workspace.Gravity = 0
                    if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,NameMon) then
                        for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                            if v.Name == Ms and v.Humanoid.Health > 0 then
                                repeat task.wait()
                                toposQ(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
                                PosMon = v.HumanoidRootPart.CFrame
                                Magnet = true
                                v.HumanoidRootPart.Size = Vector3.new(60,60,60)
                                v.HumanoidRootPart.CanCollide = false
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService('VirtualUser'):ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
                                until _G.FarmLevel == false or v.Humanoid.Health <= 0 or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                            end
                        end
                    else
                         workspace.Gravity = 196.19999694824
                        Magnet = false
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                    end
                end
            end
        end)
    end
end)  

spawn(function()
    while task.wait() do
        pcall(function()
            CheckLevel()
            for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                if _G.FarmLevel and Magnet and v.Name == Ms and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 290 then
                    v.HumanoidRootPart.CFrame = PosMon
                    v.Humanoid:ChangeState(11)
                    sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.huge)
                end
            end
        end)
    end
end)

spawn(function()
    game:GetService("RunService").Heartbeat:Connect(function()
        if _G.FarmLevel then
            if not game:GetService("Workspace"):FindFirstChild("LOL") then
                local LOL = Instance.new("Part")
                LOL.Name = "LOL"
                LOL.Parent = game.Workspace
                LOL.Anchored = true
                LOL.Transparency = 0
                LOL.Size = Vector3.new(20,-0.5,20)
                LOL.Material = "Neon"
            elseif game:GetService("Workspace"):FindFirstChild("LOL") then
                game.Workspace["LOL"].CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,-3.5,0)
            end
        else
            if game:GetService("Workspace"):FindFirstChild("LOL") then
                game:GetService("Workspace"):FindFirstChild("LOL"):Destroy()
            end
        end
    end)
end)


spawn(function()
    while wait() do
        if game.Workspace:FindFirstChild("LOL") then
            game.Workspace:FindFirstChild("LOL").Color = Color3.new(255/255,0/255,0/255)
            for i = 0,255,10 do
                wait(.1)
                if game.Workspace:FindFirstChild("LOL") then
                    game.Workspace:FindFirstChild("LOL").Color = Color3.new(255/255,i/255,0/255)
                end
            end
            for i = 255,0,-10 do
                wait(.1)
                if game.Workspace:FindFirstChild("LOL") then
                    game.Workspace:FindFirstChild("LOL").Color = Color3.new(i/255,255/255,0/255)
                end
            end
            for i = 0,255,10 do
                wait(.1)
                if game.Workspace:FindFirstChild("LOL") then
                    game.Workspace:FindFirstChild("LOL").Color = Color3.new(0/255,255/255,i/255)
                end
            end
            for i = 255,0,-10 do
                wait(.1)
                if game.Workspace:FindFirstChild("LOL") then
                    game.Workspace:FindFirstChild("LOL").Color = Color3.new(0/255,i/255,255/255)
                end
            end
            for i = 0,255,10 do
                wait(.1)
                if game.Workspace:FindFirstChild("LOL") then
                    game.Workspace:FindFirstChild("LOL").Color = Color3.new(i/255,0/255,255/255)
                end
            end
            for i = 255,0,-10 do
                wait(.1)
                if game.Workspace:FindFirstChild("LOL") then
                    game.Workspace:FindFirstChild("LOL").Color = Color3.new(255/255,0/255,i/255)
                end
            end
        end
    end
end)
