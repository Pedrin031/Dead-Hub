-- Dead Hub - Created By Pedrin031

local Neox = loadstring(game:HttpGet("https://raw.githubusercontent.com/hassanxzayn-lua/NEOXHUBMAIN/refs/heads/main/newneoxlib"))()

local Window = Neox:CreateWindow({
    Title = "Dead Hub | Dead Rails v1.9.4",
    SubTitle = "Created By Pedrin031",
    TabWidth = 120,
    Size = UDim2.fromOffset(600, 450),
    Acrylic = false,
    Theme = "Light",
    MinimizeKey = Enum.KeyCode.P
})

task.spawn(function()
    local CoreGui = game:GetService("CoreGui")
    for _, v in ipairs(CoreGui:GetDescendants()) do
        if v:IsA("Frame") or v:IsA("TextLabel") or v:IsA("TextButton") then
            if v.BackgroundColor3 == Color3.fromRGB(20, 20, 20) or v.BackgroundColor3 == Color3.fromRGB(30, 30, 30) then
                v.BackgroundColor3 = Color3.fromRGB(192, 192, 192)
            end
        end
    end
end)

local Tabs = {
    Home = Window:AddTab({ Title = " Home", Icon = "rbxassetid://7733960981" }),
    Main = Window:AddTab({ Title = " Main", Icon = "rbxassetid://7743869612" }),
    Autofarm = Window:AddTab({ Title = " Auto", Icon = "rbxassetid://7733917120" }),
    Aimbot = Window:AddTab({ Title = " Aimbot", Icon = "rbxassetid://7743878857" }),
    Misc = Window:AddTab({ Title = " Misc", Icon = "rbxassetid://7733789088" }),
    Weather = Window:AddTab({ Title = " Environment", Icon = "rbxassetid://7734068495" }),
    Performance = Window:AddTab({ Title = " Performance", Icon = "rbxassetid://7733955511" }),
    Esp = Window:AddTab({ Title = " Esp", Icon = "rbxassetid://7743875962" }),
    Train = Window:AddTab({ Title = " Train Stuff", Icon = "rbxassetid://7733954611" }),
    Teleport = Window:AddTab({ Title = " Teleport", Icon = "rbxassetid://7733992789" }),
}
Window:SelectTab(1)

local executorName = "Unknown Executor"
pcall(function()
    executorName = identifyexecutor() or "Unknown Executor"
end)

Tabs.Home:AddSection("Executor: " .. executorName)
Tabs.Home:AddSection("")

Tabs.Home:AddButton({
    Title = "Discord",
    Description = "Clique para copiar o link do nosso Discord!",
    Callback = function()
        if setclipboard then
            setclipboard("https://discord.gg/jfKVrrMx")
            print("Link do Discord copiado!")
        else
            warn("setclipboard não disponível.")
        end
    end
})

Tabs.Home:AddParagraph({
    Title = "Atualização v1.9.4",
    Content = "[+] = Adicionado     [-] = Corrigido
-----------------------------
[+] Paredes das casas transparentes
"
})

print("Dead Hub carregado com sucesso!")

with open("/mnt/data/DeadHub_Final.txt", "w", encoding="utf-8") as f:
    f.write(script_text)
