game.StarterGui:SetCore("SendNotification", {
	Title = "AutoClicker";
    Text = "Q to turn on and off";
})
SNYPASEWONTUPDATE = false
game:GetService('RunService').Stepped:connect(function()
if SNYPASEWONTUPDATE then
game:GetService("VirtualUser"):ClickButton1(Vector2.new(125,125)) 
end
end)
plr = game.Players.LocalPlayer
mouse = plr:GetMouse()
mouse.KeyDown:connect(function(key)

if key == "q" then
SNYPASEWONTUPDATE = not SNYPASEWONTUPDATE

end
end)
game.StarterGui:SetCore("SendNotification", {
	Title = "G3 Notification";
    Text = "If You Die Execute Again";
})
local player = game.Players.LocalPlayer
local mouse = player:GetMouse()
wait(1) -- load charac 
	local char = player.Character
	local char_root = char:FindFirstChild("HumanoidRootPart")
	 
mouse.Button1Down:connect(function()
    local nearest_hum = math.huge
 
    local target_root
    local target_hum
	 	    for i, v in pairs(workspace:GetChildren()) do	        local root = v:FindFirstChild("HumanoidRootPart")	        local hum = v:FindFirstChild("Humanoid")
	 
	        if root and hum and v ~= char then
           local mag = (char_root.Position - root.Position).magnitude
 
            if mag < 13 and mag < nearest_hum then
               local obstructed = false
 
                local ray = Ray.new(char_root.Position, (root.Position - char_root.Position).unit * 0)
	 	                local part = workspace:FindPartOnRay(ray, char, false, true)

                if part then
                  if part.Parent ~= v then
                     obstructed = true
                end
              end

           if obstructed == false then
                nearest_hum = mag
                   target_root = root
                    target_hum = hum
                end
           end
        end
    end
 
	    if target_root and target_hum then
	        nearest_hum = math.huge
        local behind = (target_root.CFrame * CFrame.new(8,2,-target_root.Size / 2)).p -- the behind lol
	        char_root.CFrame = CFrame.new(behind)
        local behind = (target_root.CFrame * CFrame.new(6,2,-target_root.Size / 2)).p -- the behind lol
	        char_root.CFrame = CFrame.new(behind)
        local behind = (target_root.CFrame * CFrame.new(10,3,-target_root.Size / 2)).p -- the behind lol
	        char_root.CFrame = CFrame.new(behind)
        local behind = (target_root.CFrame * CFrame.new(8,2,-target_root.Size / 2)).p -- the behind lol
	        char_root.CFrame = CFrame.new(behind)
        local behind = (target_root.CFrame * CFrame.new(10,3,-target_root.Size / 2)).p -- the behind lol
	        char_root.CFrame = CFrame.new(behind)
        local behind = (target_root.CFrame * CFrame.new(6,2,-target_root.Size / 2)).p -- the behind lol
	        char_root.CFrame = CFrame.new(behind)
target_hum:TakeDamage(0)
	    end
end)
