getgenv().AutoFarm = false
getgenv().AutoUpgrade = false

local function AutoFarm()
    while getgenv().AutoFarm do
        -- Auto Farm Logic
        print("Auto farming...")
        wait(1)
    end
end

local function AutoUpgrade()
    while getgenv().AutoUpgrade do
        -- Auto Upgrade Logic
        print("Auto upgrading units...")
        wait(2)
    end
end

-- UI Commands
print("Anime Adventures Script Loaded")
print("Commands: /farm to toggle Auto Farm, /upgrade to toggle Auto Upgrade, /teleport to teleport to spawn.")

game.Players.LocalPlayer.Chatted:Connect(function(msg)
    msg = msg:lower()
    
    if msg == "/farm" then
        getgenv().AutoFarm = not getgenv().AutoFarm
        print("Auto Farm:", getgenv().AutoFarm)
        if getgenv().AutoFarm then AutoFarm() end
        
    elseif msg == "/upgrade" then
        getgenv().AutoUpgrade = not getgenv().AutoUpgrade
        print("Auto Upgrade:", getgenv().AutoUpgrade)
        if getgenv().AutoUpgrade then AutoUpgrade() end
        
    elseif msg == "/teleport" then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(0, 10, 0)
        print("Teleported to spawn!")
    end
end)
