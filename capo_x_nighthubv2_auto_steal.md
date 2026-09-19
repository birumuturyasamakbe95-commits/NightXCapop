\-- CAPO X NIGHTHUBV2 AUTO STEAL
\-- Updated Steal Logic + Integrated UI

local player = game.Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")
local UIS = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local Stats = game:GetService("Stats")

\-- ============================================
\-- UI CREATION
\-- ============================================
local CapoXNighthubv2 = Instance.new("ScreenGui")
CapoXNighthubv2.Name = "CapoXNighthubv2"
CapoXNighthubv2.IgnoreGuiInset = true
CapoXNighthubv2.ResetOnSpawn = false
CapoXNighthubv2.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
CapoXNighthubv2.Parent = playerGui

\-- ========== MAIN FULL UI ==========
local Main = Instance.new("Frame")
Main.Name = "Main"
Main.Active = true
Main.ClipsDescendants = true
Main.Position = UDim2.new(0.5, -155, 0.3, 0)
Main.Size = UDim2.new(0, 310, 0, 0)
Main.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Main.BorderSizePixel = 0
Main.AutomaticSize = Enum.AutomaticSize.Y
Main.Parent = CapoXNighthubv2

local UICorner = Instance.new("UICorner")
UICorner.CornerRadius = UDim.new(0, 16)
UICorner.Parent = Main

local UIGradient = Instance.new("UIGradient")
UIGradient.Color = ColorSequence.new(Color3.fromRGB(34, 2, 4), Color3.fromRGB(0, 0, 0))
UIGradient.Rotation = 90
UIGradient.Parent = Main

local UIStroke = Instance.new("UIStroke")
UIStroke.Thickness = 3
UIStroke.Color = Color3.fromRGB(235, 20, 26)
UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
UIStroke.Parent = Main

local UIScale = Instance.new("UIScale")
UIScale.Scale = 0.62
UIScale.Parent = Main

local Background = Instance.new("ImageLabel")
Background.Size = UDim2.new(1, 0, 1, 0)
Background.BackgroundTransparency = 1
Background.BorderSizePixel = 0
Background.Image = "rbxassetid://80161793688220"
Background.ImageTransparency = 0.15
Background.ScaleType = Enum.ScaleType.Crop
Background.Parent = Main

local UICorner2 = Instance.new("UICorner")
UICorner2.CornerRadius = UDim.new(0, 16)
UICorner2.Parent = Background

local TitleBar = Instance.new("Frame")
TitleBar.ZIndex = 3
TitleBar.Size = UDim2.new(1, 0, 0, 54)
TitleBar.BackgroundTransparency = 1
TitleBar.BorderSizePixel = 0
TitleBar.Parent = Main

local Title = Instance.new("TextLabel")
Title.ZIndex = 4
Title.Position = UDim2.new(0, 16, 0, 9)
Title.Size = UDim2.new(1, -120, 0, 22)
Title.BackgroundTransparency = 1
Title.Text = "Capo X Nighthubv2"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.TextSize = 14
Title.Font = Enum.Font.GothamBlack
Title.TextXAlignment = Enum.TextXAlignment.Left
Title.TextTruncate = Enum.TextTruncate.AtEnd
Title.TextStrokeTransparency = 0.55
Title.Parent = TitleBar

local UIStroke2 = Instance.new("UIStroke")
UIStroke2.Thickness = 1.6
UIStroke2.Transparency = 0.35
UIStroke2.Color = Color3.fromRGB(235, 20, 26)
UIStroke2.Parent = Title

local Watermark = Instance.new("TextLabel")
Watermark.ZIndex = 4
Watermark.Position = UDim2.new(0, 16, 0, 31)
Watermark.Size = UDim2.new(1, -120, 0, 14)
Watermark.BackgroundTransparency = 1
Watermark.Text = "Capo X Nighthubv2"
Watermark.TextColor3 = Color3.fromRGB(235, 20, 26)
Watermark.TextSize = 11
Watermark.Font = Enum.Font.GothamBold
Watermark.TextXAlignment = Enum.TextXAlignment.Left
Watermark.TextTruncate = Enum.TextTruncate.AtEnd
Watermark.TextStrokeTransparency = 0.5
Watermark.Parent = TitleBar

\-- Minimize button ("-")
local MinBtn = Instance.new("TextButton")
MinBtn.ZIndex = 4
MinBtn.Position = UDim2.new(1, -64, 0.5, -12)
MinBtn.Size = UDim2.new(0, 48, 0, 24)
MinBtn.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
MinBtn.BorderSizePixel = 0
MinBtn.Text = "-"
MinBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
MinBtn.TextSize = 18
MinBtn.Font = Enum.Font.GothamBold
MinBtn.AutoButtonColor = false
MinBtn.Parent = TitleBar

local UICorner3 = Instance.new("UICorner")
UICorner3.Parent = MinBtn

local Lock = Instance.new("TextButton")
Lock.ZIndex = 4
Lock.Position = UDim2.new(1, -96, 0.5, -12)
Lock.Size = UDim2.new(0, 28, 0, 24)
Lock.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Lock.BorderSizePixel = 0
Lock.Text = "🔓"
Lock.TextColor3 = Color3.fromRGB(255, 255, 255)
Lock.TextSize = 14
Lock.Font = Enum.Font.GothamBold
Lock.AutoButtonColor = false
Lock.Parent = TitleBar

local UICorner4 = Instance.new("UICorner")
UICorner4.Parent = Lock

local HeaderLine = Instance.new("Frame")
HeaderLine.ZIndex = 3
HeaderLine.Position = UDim2.new(0, 16, 0, 54)
HeaderLine.Size = UDim2.new(1, -32, 0, 1)
HeaderLine.BackgroundColor3 = Color3.fromRGB(235, 20, 26)
HeaderLine.BackgroundTransparency = 0.6
HeaderLine.BorderSizePixel = 0
HeaderLine.Parent = Main

local Body = Instance.new("Frame")
Body.ZIndex = 3
Body.Position = UDim2.new(0, 0, 0, 64)
Body.Size = UDim2.new(1, 0, 0, 0)
Body.BackgroundTransparency = 1
Body.BorderSizePixel = 0
Body.AutomaticSize = Enum.AutomaticSize.Y
Body.Parent = Main

local BodyLayout = Instance.new("UIListLayout")
BodyLayout.Padding = UDim.new(0, 4)
BodyLayout.FillDirection = Enum.FillDirection.Vertical
BodyLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
BodyLayout.SortOrder = Enum.SortOrder.LayoutOrder
BodyLayout.Parent = Body

\-- AUTO STEAL ROW
local AutoStealRow = Instance.new("Frame")
AutoStealRow.ZIndex = 4
AutoStealRow.LayoutOrder = 1
AutoStealRow.Size = UDim2.new(1, -32, 0, 36)
AutoStealRow.BackgroundColor3 = Color3.fromRGB(18, 18, 20)
AutoStealRow.BackgroundTransparency = 0.25
AutoStealRow.BorderSizePixel = 0
AutoStealRow.Parent = Body

local UICorner21 = Instance.new("UICorner")
UICorner21.CornerRadius = UDim.new(0, 10)
UICorner21.Parent = AutoStealRow

local AccentBar2 = Instance.new("Frame")
AccentBar2.ZIndex = 5
AccentBar2.Position = UDim2.new(0, 9, 0.5, -9)
AccentBar2.Size = UDim2.new(0, 3, 0, 18)
AccentBar2.BackgroundColor3 = Color3.fromRGB(235, 20, 26)
AccentBar2.BorderSizePixel = 0
AccentBar2.Parent = AutoStealRow

local UICorner22 = Instance.new("UICorner")
UICorner22.CornerRadius = UDim.new(1, 0)
UICorner22.Parent = AccentBar2

local Label2 = Instance.new("TextLabel")
Label2.ZIndex = 5
Label2.Position = UDim2.new(0, 20, 0, 0)
Label2.Size = UDim2.new(1, -110, 1, 0)
Label2.BackgroundTransparency = 1
Label2.Text = "Auto Steal"
Label2.TextColor3 = Color3.fromRGB(255, 255, 255)
Label2.TextSize = 13
Label2.Font = Enum.Font.GothamBold
Label2.TextXAlignment = Enum.TextXAlignment.Left
Label2.TextTruncate = Enum.TextTruncate.AtEnd
Label2.TextStrokeTransparency = 0.6
Label2.Parent = AutoStealRow

local Hit = Instance.new("TextButton")
Hit.ZIndex = 6
Hit.Size = UDim2.new(1, 0, 1, 0)
Hit.BackgroundTransparency = 1
Hit.Text = ""
Hit.AutoButtonColor = false
Hit.Parent = AutoStealRow

local Track = Instance.new("Frame")
Track.ZIndex = 7
Track.Position = UDim2.new(1, -56, 0.5, -12)
Track.Size = UDim2.new(0, 46, 0, 24)
Track.BackgroundColor3 = Color3.fromRGB(235, 20, 26)
Track.BorderSizePixel = 0
Track.Parent = AutoStealRow

local UICorner23 = Instance.new("UICorner")
UICorner23.CornerRadius = UDim.new(1, 0)
UICorner23.Parent = Track

local UIStroke5 = Instance.new("UIStroke")
UIStroke5.Transparency = 0.5
UIStroke5.Color = Color3.fromRGB(255, 255, 255)
UIStroke5.Parent = Track

local Knob = Instance.new("Frame")
Knob.ZIndex = 8
Knob.Position = UDim2.new(1, -21, 0.5, -9)
Knob.Size = UDim2.new(0, 18, 0, 18)
Knob.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Knob.BorderSizePixel = 0
Knob.Parent = Track

local UICorner24 = Instance.new("UICorner")
UICorner24.CornerRadius = UDim.new(1, 0)
UICorner24.Parent = Knob

\-- MODE ROW
local ModeRow = Instance.new("Frame")
ModeRow.ZIndex = 4
ModeRow.LayoutOrder = 2
ModeRow.Size = UDim2.new(1, -32, 0, 30)
ModeRow.BackgroundTransparency = 1
ModeRow.BorderSizePixel = 0
ModeRow.Parent = Body

local UIListLayout = Instance.new("UIListLayout")
UIListLayout.Padding = UDim.new(0, 6)
UIListLayout.FillDirection = Enum.FillDirection.Horizontal
UIListLayout.VerticalAlignment = Enum.VerticalAlignment.Center
UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
UIListLayout.Parent = ModeRow

local NORMAL = Instance.new("TextButton")
NORMAL.ZIndex = 5
NORMAL.LayoutOrder = 1
NORMAL.Size = UDim2.new(0.5, -5, 1, 0)
NORMAL.BackgroundColor3 = Color3.fromRGB(235, 20, 26)
NORMAL.BorderSizePixel = 0
NORMAL.Text = "NORMAL"
NORMAL.TextColor3 = Color3.fromRGB(255, 255, 255)
NORMAL.TextSize = 12
NORMAL.Font = Enum.Font.GothamBold
NORMAL.AutoButtonColor = false
NORMAL.Parent = ModeRow

local UICorner5 = Instance.new("UICorner")
UICorner5.CornerRadius = UDim.new(0, 9)
UICorner5.Parent = NORMAL

local SEMI = Instance.new("TextButton")
SEMI.ZIndex = 5
SEMI.LayoutOrder = 2
SEMI.Size = UDim2.new(0.5, -5, 1, 0)
SEMI.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
SEMI.BackgroundTransparency = 0.45
SEMI.BorderSizePixel = 0
SEMI.Text = "SEMI"
SEMI.TextColor3 = Color3.fromRGB(155, 155, 155)
SEMI.TextSize = 12
SEMI.Font = Enum.Font.GothamBold
SEMI.AutoButtonColor = false
SEMI.Parent = ModeRow

local UICorner6 = Instance.new("UICorner")
UICorner6.CornerRadius = UDim.new(0, 9)
UICorner6.Parent = SEMI

\-- VERSION ROW
local VersionRow = Instance.new("Frame")
VersionRow.ZIndex = 4
VersionRow.LayoutOrder = 3
VersionRow.Size = UDim2.new(1, -32, 0, 30)
VersionRow.BackgroundTransparency = 1
VersionRow.BorderSizePixel = 0
VersionRow.Parent = Body

local UIListLayout2 = Instance.new("UIListLayout")
UIListLayout2.Padding = UDim.new(0, 6)
UIListLayout2.FillDirection = Enum.FillDirection.Horizontal
UIListLayout2.VerticalAlignment = Enum.VerticalAlignment.Center
UIListLayout2.SortOrder = Enum.SortOrder.LayoutOrder
UIListLayout2.Parent = VersionRow

local V1 = Instance.new("TextButton")
V1.ZIndex = 5
V1.LayoutOrder = 1
V1.Size = UDim2.new(0.333333, -4, 1, 0)
V1.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
V1.BackgroundTransparency = 0.45
V1.BorderSizePixel = 0
V1.Text = "V1"
V1.TextColor3 = Color3.fromRGB(155, 155, 155)
V1.TextSize = 12
V1.Font = Enum.Font.GothamBold
V1.AutoButtonColor = false
V1.Parent = VersionRow

local UICorner7 = Instance.new("UICorner")
UICorner7.CornerRadius = UDim.new(0, 9)
UICorner7.Parent = V1

local V2 = Instance.new("TextButton")
V2.ZIndex = 5
V2.LayoutOrder = 2
V2.Size = UDim2.new(0.333333, -4, 1, 0)
V2.BackgroundColor3 = Color3.fromRGB(235, 20, 26)
V2.BorderSizePixel = 0
V2.Text = "V2"
V2.TextColor3 = Color3.fromRGB(255, 255, 255)
V2.TextSize = 12
V2.Font = Enum.Font.GothamBold
V2.AutoButtonColor = false
V2.Parent = VersionRow

local UICorner8 = Instance.new("UICorner")
UICorner8.CornerRadius = UDim.new(0, 9)
UICorner8.Parent = V2

local V3 = Instance.new("TextButton")
V3.ZIndex = 5
V3.LayoutOrder = 3
V3.Size = UDim2.new(0.333333, -4, 1, 0)
V3.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
V3.BackgroundTransparency = 0.45
V3.BorderSizePixel = 0
V3.Text = "V3"
V3.TextColor3 = Color3.fromRGB(155, 155, 155)
V3.TextSize = 12
V3.Font = Enum.Font.GothamBold
V3.AutoButtonColor = false
V3.Parent = VersionRow

local UICorner9 = Instance.new("UICorner")
UICorner9.CornerRadius = UDim.new(0, 9)
UICorner9.Parent = V3

\-- STOP ROW
local StopRow = Instance.new("Frame")
StopRow.ZIndex = 4
StopRow.LayoutOrder = 4
StopRow.Size = UDim2.new(1, -32, 0, 26)
StopRow.BackgroundTransparency = 1
StopRow.BorderSizePixel = 0
StopRow.Parent = Body
StopRow.Visible = false

local UIListLayout3 = Instance.new("UIListLayout")
UIListLayout3.Padding = UDim.new(0, 6)
UIListLayout3.FillDirection = Enum.FillDirection.Horizontal
UIListLayout3.VerticalAlignment = Enum.VerticalAlignment.Center
UIListLayout3.SortOrder = Enum.SortOrder.LayoutOrder
UIListLayout3.Parent = StopRow

local \_75 = Instance.new("TextButton")
\_75.ZIndex = 5
\_75.LayoutOrder = 1
\_75.Size = UDim2.new(0.25, -5, 1, 0)
\_75.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
\_75.BackgroundTransparency = 0.45
\_75.BorderSizePixel = 0
\_75.Text = "75"
\_75.TextColor3 = Color3.fromRGB(155, 155, 155)
\_75.TextSize = 11
\_75.Font = Enum.Font.GothamBold
\_75.AutoButtonColor = false
\_75.Parent = StopRow

local UICorner10 = Instance.new("UICorner")
UICorner10.CornerRadius = UDim.new(0, 9)
UICorner10.Parent = \_75

local \_80 = Instance.new("TextButton")
\_80.ZIndex = 5
\_80.LayoutOrder = 2
\_80.Size = UDim2.new(0.25, -5, 1, 0)
\_80.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
\_80.BackgroundTransparency = 0.45
\_80.BorderSizePixel = 0
\_80.Text = "80"
\_80.TextColor3 = Color3.fromRGB(155, 155, 155)
\_80.TextSize = 11
\_80.Font = Enum.Font.GothamBold
\_80.AutoButtonColor = false
\_80.Parent = StopRow

local UICorner11 = Instance.new("UICorner")
UICorner11.CornerRadius = UDim.new(0, 9)
UICorner11.Parent = \_80

local \_85 = Instance.new("TextButton")
\_85.ZIndex = 5
\_85.LayoutOrder = 3
\_85.Size = UDim2.new(0.25, -5, 1, 0)
\_85.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
\_85.BackgroundTransparency = 0.45
\_85.BorderSizePixel = 0
\_85.Text = "85"
\_85.TextColor3 = Color3.fromRGB(155, 155, 155)
\_85.TextSize = 11
\_85.Font = Enum.Font.GothamBold
\_85.AutoButtonColor = false
\_85.Parent = StopRow

local UICorner12 = Instance.new("UICorner")
UICorner12.CornerRadius = UDim.new(0, 9)
UICorner12.Parent = \_85

local \_90 = Instance.new("TextButton")
\_90.ZIndex = 5
\_90.LayoutOrder = 4
\_90.Size = UDim2.new(0.25, -5, 1, 0)
\_90.BackgroundColor3 = Color3.fromRGB(235, 20, 26)
\_90.BorderSizePixel = 0
\_90.Text = "90"
\_90.TextColor3 = Color3.fromRGB(255, 255, 255)
\_90.TextSize = 11
\_90.Font = Enum.Font.GothamBold
\_90.AutoButtonColor = false
\_90.Parent = StopRow

local UICorner13 = Instance.new("UICorner")
UICorner13.CornerRadius = UDim.new(0, 9)
UICorner13.Parent = \_90

\-- RAGDOLL ROW
local RagdollRow = Instance.new("Frame")
RagdollRow.ZIndex = 4
RagdollRow.LayoutOrder = 5
RagdollRow.Size = UDim2.new(1, -32, 0, 36)
RagdollRow.BackgroundColor3 = Color3.fromRGB(18, 18, 20)
RagdollRow.BackgroundTransparency = 0.25
RagdollRow.BorderSizePixel = 0
RagdollRow.Parent = Body

local UICorner25 = Instance.new("UICorner")
UICorner25.CornerRadius = UDim.new(0, 10)
UICorner25.Parent = RagdollRow

local AccentBar3 = Instance.new("Frame")
AccentBar3.ZIndex = 5
AccentBar3.Position = UDim2.new(0, 9, 0.5, -9)
AccentBar3.Size = UDim2.new(0, 3, 0, 18)
AccentBar3.BackgroundColor3 = Color3.fromRGB(235, 20, 26)
AccentBar3.BorderSizePixel = 0
AccentBar3.Parent = RagdollRow

local UICorner26 = Instance.new("UICorner")
UICorner26.CornerRadius = UDim.new(1, 0)
UICorner26.Parent = AccentBar3

local Label3 = Instance.new("TextLabel")
Label3.ZIndex = 5
Label3.Position = UDim2.new(0, 20, 0, 0)
Label3.Size = UDim2.new(1, -110, 1, 0)
Label3.BackgroundTransparency = 1
Label3.Text = "Ragdoll Steal"
Label3.TextColor3 = Color3.fromRGB(255, 255, 255)
Label3.TextSize = 13
Label3.Font = Enum.Font.GothamBold
Label3.TextXAlignment = Enum.TextXAlignment.Left
Label3.TextTruncate = Enum.TextTruncate.AtEnd
Label3.TextStrokeTransparency = 0.6
Label3.Parent = RagdollRow

local Hit2 = Instance.new("TextButton")
Hit2.ZIndex = 6
Hit2.Size = UDim2.new(1, 0, 1, 0)
Hit2.BackgroundTransparency = 1
Hit2.Text = ""
Hit2.AutoButtonColor = false
Hit2.Parent = RagdollRow

local Track2 = Instance.new("Frame")
Track2.ZIndex = 7
Track2.Position = UDim2.new(1, -56, 0.5, -12)
Track2.Size = UDim2.new(0, 46, 0, 24)
Track2.BackgroundColor3 = Color3.fromRGB(48, 48, 52)
Track2.BorderSizePixel = 0
Track2.Parent = RagdollRow

local UICorner27 = Instance.new("UICorner")
UICorner27.CornerRadius = UDim.new(1, 0)
UICorner27.Parent = Track2

local UIStroke6 = Instance.new("UIStroke")
UIStroke6.Transparency = 0.5
UIStroke6.Color = Color3.fromRGB(255, 255, 255)
UIStroke6.Parent = Track2

local Knob2 = Instance.new("Frame")
Knob2.ZIndex = 8
Knob2.Position = UDim2.new(0, 3, 0.5, -9)
Knob2.Size = UDim2.new(0, 18, 0, 18)
Knob2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Knob2.BorderSizePixel = 0
Knob2.Parent = Track2

local UICorner28 = Instance.new("UICorner")
UICorner28.CornerRadius = UDim.new(1, 0)
UICorner28.Parent = Knob2

\-- RADIUS ROW
local RadiusRow = Instance.new("Frame")
RadiusRow.ZIndex = 4
RadiusRow.LayoutOrder = 6
RadiusRow.Size = UDim2.new(1, -32, 0, 34)
RadiusRow.BackgroundColor3 = Color3.fromRGB(18, 18, 20)
RadiusRow.BackgroundTransparency = 0.25
RadiusRow.BorderSizePixel = 0
RadiusRow.Parent = Body

local UICorner14 = Instance.new("UICorner")
UICorner14.CornerRadius = UDim.new(0, 10)
UICorner14.Parent = RadiusRow

local AccentBar = Instance.new("Frame")
AccentBar.ZIndex = 5
AccentBar.Position = UDim2.new(0, 9, 0.5, -9)
AccentBar.Size = UDim2.new(0, 3, 0, 18)
AccentBar.BackgroundColor3 = Color3.fromRGB(235, 20, 26)
AccentBar.BorderSizePixel = 0
AccentBar.Parent = RadiusRow

local UICorner15 = Instance.new("UICorner")
UICorner15.CornerRadius = UDim.new(1, 0)
UICorner15.Parent = AccentBar

local Label = Instance.new("TextLabel")
Label.ZIndex = 5
Label.Position = UDim2.new(0, 20, 0, 0)
Label.Size = UDim2.new(1, -110, 1, 0)
Label.BackgroundTransparency = 1
Label.Text = "Normal V2 Radius"
Label.TextColor3 = Color3.fromRGB(255, 255, 255)
Label.TextSize = 13
Label.Font = Enum.Font.GothamBold
Label.TextXAlignment = Enum.TextXAlignment.Left
Label.TextTruncate = Enum.TextTruncate.AtEnd
Label.TextStrokeTransparency = 0.6
Label.Parent = RadiusRow

local Value = Instance.new("TextBox")
Value.ZIndex = 6
Value.ClipsDescendants = true
Value.Position = UDim2.new(1, -66, 0.5, -12)
Value.Size = UDim2.new(0, 56, 0, 25)
Value.BackgroundColor3 = Color3.fromRGB(18, 18, 18)
Value.BorderSizePixel = 0
Value.Text = "62"
Value.TextColor3 = Color3.fromRGB(235, 20, 26)
Value.TextSize = 13
Value.Font = Enum.Font.GothamBold
Value.ClearTextOnFocus = true
Value.Parent = RadiusRow

local UICorner16 = Instance.new("UICorner")
UICorner16.CornerRadius = UDim.new(0, 6)
UICorner16.Parent = Value

local UIStroke3 = Instance.new("UIStroke")
UIStroke3.Color = Color3.fromRGB(235, 20, 26)
UIStroke3.Transparency = 0.5
UIStroke3.Parent = Value

\-- CHANGE GUI
local ChangeGui = Instance.new("TextButton")
ChangeGui.ZIndex = 5
ChangeGui.LayoutOrder = 7
ChangeGui.Size = UDim2.new(1, -32, 0, 28)
ChangeGui.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ChangeGui.BackgroundTransparency = 0.45
ChangeGui.BorderSizePixel = 0
ChangeGui.Text = "Color Theme: RED"
ChangeGui.TextColor3 = Color3.fromRGB(255, 255, 255)
ChangeGui.TextSize = 12
ChangeGui.Font = Enum.Font.GothamBold
ChangeGui.AutoButtonColor = false
ChangeGui.Parent = Body

local UICorner17 = Instance.new("UICorner")
UICorner17.CornerRadius = UDim.new(0, 9)
UICorner17.Parent = ChangeGui

\-- STEAL BAR
local StealBar = Instance.new("Frame")
StealBar.ZIndex = 4
StealBar.ClipsDescendants = true
StealBar.LayoutOrder = 8
StealBar.Size = UDim2.new(1, -32, 0, 26)
StealBar.BackgroundColor3 = Color3.fromRGB(16, 16, 16)
StealBar.BackgroundTransparency = 0.15
StealBar.BorderSizePixel = 0
StealBar.Parent = Body

local UICorner18 = Instance.new("UICorner")
UICorner18.CornerRadius = UDim.new(1, 0)
UICorner18.Parent = StealBar

local UIGradient2 = Instance.new("UIGradient")
UIGradient2.Color = ColorSequence.new(Color3.fromRGB(30, 30, 30), Color3.fromRGB(8, 8, 8))
UIGradient2.Rotation = 90
UIGradient2.Parent = StealBar

local UIStroke4 = Instance.new("UIStroke")
UIStroke4.Color = Color3.fromRGB(235, 20, 26)
UIStroke4.Thickness = 1.2
UIStroke4.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
UIStroke4.Transparency = 0.7
UIStroke4.Parent = StealBar

local Fill = Instance.new("Frame")
Fill.ZIndex = 5
Fill.Size = UDim2.new(0, 0, 1, 0)
Fill.BackgroundColor3 = Color3.fromRGB(235, 20, 26)
Fill.BorderSizePixel = 0
Fill.Parent = StealBar

local UICorner19 = Instance.new("UICorner")
UICorner19.CornerRadius = UDim.new(1, 0)
UICorner19.Parent = Fill

local UIGradient3 = Instance.new("UIGradient")
UIGradient3.Color = ColorSequence.new(Color3.fromRGB(242, 102, 106), Color3.fromRGB(235, 20, 26))
UIGradient3.Parent = Fill

local Shine = Instance.new("Frame")
Shine.ZIndex = 6
Shine.Size = UDim2.new(1, 0, 0.45, 0)
Shine.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Shine.BackgroundTransparency = 0.78
Shine.BorderSizePixel = 0
Shine.Parent = Fill

local UICorner20 = Instance.new("UICorner")
UICorner20.CornerRadius = UDim.new(1, 0)
UICorner20.Parent = Shine

local Percent = Instance.new("TextLabel")
Percent.ZIndex = 7
Percent.Size = UDim2.new(1, 0, 1, 0)
Percent.BackgroundTransparency = 1
Percent.Text = "0%"
Percent.TextColor3 = Color3.fromRGB(255, 255, 255)
Percent.TextSize = 13
Percent.Font = Enum.Font.GothamBlack
Percent.TextStrokeTransparency = 0.25
Percent.Parent = StealBar

\-- SPACER
local Spacer = Instance.new("Frame")
Spacer.LayoutOrder = 9
Spacer.Size = UDim2.new(1, 0, 0, 6)
Spacer.BackgroundTransparency = 1
Spacer.BorderSizePixel = 0
Spacer.Parent = Body

\-- ========== MINIMIZED BAR ==========
local MinimizedBar = Instance.new("Frame")
MinimizedBar.Name = "MinimizedBar"
MinimizedBar.Size = UDim2.new(0, 210, 0, 32)
MinimizedBar.Position = Main.Position
MinimizedBar.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
MinimizedBar.BorderSizePixel = 0
MinimizedBar.Visible = false
MinimizedBar.Parent = CapoXNighthubv2

local BarCorner = Instance.new("UICorner")
BarCorner.CornerRadius = UDim.new(0, 12)
BarCorner.Parent = MinimizedBar

local BarGradient = Instance.new("UIGradient")
BarGradient.Color = ColorSequence.new(Color3.fromRGB(34, 2, 4), Color3.fromRGB(0, 0, 0))
BarGradient.Rotation = 90
BarGradient.Parent = MinimizedBar

local BarStroke = Instance.new("UIStroke")
BarStroke.Thickness = 2
BarStroke.Color = Color3.fromRGB(235, 20, 26)
BarStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
BarStroke.Parent = MinimizedBar

local BarBackground = Instance.new("ImageLabel")
BarBackground.Size = UDim2.new(1, 0, 1, 0)
BarBackground.BackgroundTransparency = 1
BarBackground.BorderSizePixel = 0
BarBackground.Image = "rbxassetid://80161793688220"
BarBackground.ImageTransparency = 0.15
BarBackground.ScaleType = Enum.ScaleType.Crop
BarBackground.Parent = MinimizedBar

local BarCorner2 = Instance.new("UICorner")
BarCorner2.CornerRadius = UDim.new(0, 12)
BarCorner2.Parent = BarBackground

local BarLabel = Instance.new("TextLabel")
BarLabel.ZIndex = 4
BarLabel.Size = UDim2.new(1, -40, 1, 0)
BarLabel.Position = UDim2.new(0, 10, 0, 0)
BarLabel.BackgroundTransparency = 1
BarLabel.Text = "Capo X Nighthubv2 | FPS: 0 | Ping: 0 ms"
BarLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
BarLabel.TextSize = 12
BarLabel.Font = Enum.Font.GothamBold
BarLabel.TextXAlignment = Enum.TextXAlignment.Left
BarLabel.TextTruncate = Enum.TextTruncate.AtEnd
BarLabel.Parent = MinimizedBar

local RestoreBtn = Instance.new("TextButton")
RestoreBtn.ZIndex = 4
RestoreBtn.Position = UDim2.new(1, -34, 0.5, -12)
RestoreBtn.Size = UDim2.new(0, 24, 0, 24)
RestoreBtn.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
RestoreBtn.BorderSizePixel = 0
RestoreBtn.Text = "+"
RestoreBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
RestoreBtn.TextSize = 18
RestoreBtn.Font = Enum.Font.GothamBold
RestoreBtn.AutoButtonColor = false
RestoreBtn.Parent = MinimizedBar

local BarCorner3 = Instance.new("UICorner")
BarCorner3.CornerRadius = UDim.new(0, 6)
BarCorner3.Parent = RestoreBtn

\-- ============================================
\-- DRAGGING
\-- ============================================
local isDragging = false
local dragStart, startPos
local locked = false

local function setupDrag(frame, trigger)
trigger.InputBegan:Connect(function(input)
if locked then return end
if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
isDragging = true
dragStart = input.Position
startPos = frame.Position
input.Changed:Connect(function()
if input.UserInputState == Enum.UserInputState.End then
isDragging = false
end
end)
end
end)
end

UIS.InputChanged:Connect(function(input)
if not isDragging or locked then return end
if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
local target = Main.Visible and Main or (MinimizedBar.Visible and MinimizedBar)
if target then
target.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + input.Position.X - dragStart.X,
startPos.Y.Scale, startPos.Y.Offset + input.Position.Y - dragStart.Y)
end
end
end)

setupDrag(Main, TitleBar)
setupDrag(MinimizedBar, MinimizedBar)

\-- ============================================
\-- MINIMIZE / RESTORE
\-- ============================================
local minimized = false

local function updateMinimize()
if minimized then
MinimizedBar.Position = Main.Position
Main.Visible = false
MinimizedBar.Visible = true
MinBtn.Text = "+"
else
Main.Position = MinimizedBar.Position
MinimizedBar.Visible = false
Main.Visible = true
MinBtn.Text = "-"
end
end

MinBtn.MouseButton1Click:Connect(function()
minimized = not minimized
updateMinimize()
end)

RestoreBtn.MouseButton1Click:Connect(function()
if minimized then
minimized = false
updateMinimize()
end
end)

\-- ============================================
\-- FPS / PING UPDATE
\-- ============================================
local fpsCounter = 0
local function updateStats()
local ping = 0
pcall(function()
ping = math.floor(Stats.Network.ServerStatsItem\["Data Ping"\]:GetValue())
end)
BarLabel.Text = string.format("Capo X Nighthubv2 | FPS: %d | Ping: %d ms", fpsCounter, ping)
fpsCounter = 0
end

RunService.RenderStepped:Connect(function()
fpsCounter = fpsCounter + 1
end)

task.spawn(function()
while true do
task.wait(1)
updateStats()
end
end)

\-- ============================================
\-- UI THEMES & CONTROLS
\-- ============================================
local themes = {
{name = "RED", color = Color3.fromRGB(235, 20, 26), bg = "rbxassetid://80161793688220", grad1 = Color3.fromRGB(34, 2, 4), grad2 = Color3.fromRGB(0, 0, 0)},
{name = "BLACK", color = Color3.fromRGB(245, 245, 245), bg = "rbxassetid://102663198942761", grad1 = Color3.fromRGB(10, 10, 12), grad2 = Color3.fromRGB(0, 0, 0)},
{name = "PINK", color = Color3.fromRGB(255, 20, 140), bg = "rbxassetid://117076342830942", grad1 = Color3.fromRGB(38, 2, 24), grad2 = Color3.fromRGB(0, 0, 0)},
{name = "BLUE", color = Color3.fromRGB(40, 100, 255), bg = "rbxassetid://119302971725227", grad1 = Color3.fromRGB(4, 12, 46), grad2 = Color3.fromRGB(0, 0, 0)},
}

local themeIndex = 1
local autoStealState = true
local ragdollState = false

\-- State and logic forward references
local Steal = {
AutoStealEnabled = true,
StealRadius = 62,
StealDuration = 1.3,
Mode = 1,
Data = {},
}

local startAutoSteal, stopAutoSteal

local function applyTheme(index)
local theme = themes\[index\]

```
UIStroke.Color = theme.color
UIStroke2.Color = theme.color
UIStroke3.Color = theme.color
UIStroke4.Color = theme.color
BarStroke.Color = theme.color
Watermark.TextColor3 = theme.color
HeaderLine.BackgroundColor3 = theme.color
AccentBar.BackgroundColor3 = theme.color
AccentBar2.BackgroundColor3 = theme.color
AccentBar3.BackgroundColor3 = theme.color
Value.TextColor3 = theme.color

Background.Image = theme.bg
Background.Visible = true
BarBackground.Image = theme.bg

UIGradient.Color = ColorSequence.new(theme.grad1, theme.grad2)
BarGradient.Color = ColorSequence.new(theme.grad1, theme.grad2)

if autoStealState then Track.BackgroundColor3 = theme.color end
if ragdollState then Track2.BackgroundColor3 = theme.color end

if NORMAL.BackgroundColor3 == Color3.fromRGB(235, 20, 26) then
    NORMAL.BackgroundColor3 = theme.color
end
if V2.BackgroundColor3 == Color3.fromRGB(235, 20, 26) then
    V2.BackgroundColor3 = theme.color
end
if _90.BackgroundColor3 == Color3.fromRGB(235, 20, 26) then
    _90.BackgroundColor3 = theme.color
end

ChangeGui.Text = "Color Theme: " .. theme.name

```

end

local function toggleSwitch(track, knob, state)
knob.Position = state and UDim2.new(1, -21, 0.5, -9) or UDim2.new(0, 3, 0.5, -9)
track.BackgroundColor3 = state and themes\[themeIndex\].color or Color3.fromRGB(48, 48, 52)
end

toggleSwitch(Track, Knob, autoStealState)
toggleSwitch(Track2, Knob2, ragdollState)

Lock.MouseButton1Click:Connect(function()
locked = not locked
Lock.Text = locked and "🔒" or "🔓"
end)

local function setMode(activeBtn, inactiveBtn)
activeBtn.BackgroundColor3 = themes\[themeIndex\].color
activeBtn.BackgroundTransparency = 0
activeBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
inactiveBtn.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
inactiveBtn.BackgroundTransparency = 0.45
inactiveBtn.TextColor3 = Color3.fromRGB(155, 155, 155)
end

NORMAL.MouseButton1Click:Connect(function() setMode(NORMAL, SEMI) end)
SEMI.MouseButton1Click:Connect(function() setMode(SEMI, NORMAL) end)

local function setVersion(activeBtn)
for \_, btn in ipairs({V1, V2, V3}) do
if btn == activeBtn then
btn.BackgroundColor3 = themes\[themeIndex\].color
btn.BackgroundTransparency = 0
btn.TextColor3 = Color3.fromRGB(255, 255, 255)
else
btn.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
btn.BackgroundTransparency = 0.45
btn.TextColor3 = Color3.fromRGB(155, 155, 155)
end
end
StopRow.Visible = (activeBtn == V2)
end

V1.MouseButton1Click:Connect(function() setVersion(V1) end)
V2.MouseButton1Click:Connect(function() setVersion(V2) end)
V3.MouseButton1Click:Connect(function() setVersion(V3) end)

local function setStop(activeBtn)
for \_, btn in ipairs({\_75, \_80, \_85, \_90}) do
if btn == activeBtn then
btn.BackgroundColor3 = themes\[themeIndex\].color
btn.BackgroundTransparency = 0
btn.TextColor3 = Color3.fromRGB(255, 255, 255)
else
btn.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
btn.BackgroundTransparency = 0.45
btn.TextColor3 = Color3.fromRGB(155, 155, 155)
end
end
end

\_75.MouseButton1Click:Connect(function() setStop(\_75); Steal.Mode = 4 end)
\_80.MouseButton1Click:Connect(function() setStop(\_80); Steal.Mode = 3 end)
\_85.MouseButton1Click:Connect(function() setStop(\_85); Steal.Mode = 2 end)
\_90.MouseButton1Click:Connect(function() setStop(\_90); Steal.Mode = 1 end)

Hit.MouseButton1Click:Connect(function()
autoStealState = not autoStealState
toggleSwitch(Track, Knob, autoStealState)
Steal.AutoStealEnabled = autoStealState
if autoStealState then startAutoSteal() else stopAutoSteal() end
end)

Hit2.MouseButton1Click:Connect(function()
ragdollState = not ragdollState
toggleSwitch(Track2, Knob2, ragdollState)
end)

Value.FocusLost:Connect(function(enterPressed)
if enterPressed then
local num = tonumber(Value.Text)
if num and num > 0 then
Steal.StealRadius = num
Value.Text = tostring(num)
else
Value.Text = tostring(Steal.StealRadius)
end
end
end)

ChangeGui.MouseButton1Click:Connect(function()
themeIndex = themeIndex % #themes + 1
applyTheme(themeIndex)
toggleSwitch(Track, Knob, autoStealState)
toggleSwitch(Track2, Knob2, ragdollState)
setMode(NORMAL, SEMI)
setVersion(V2)
setStop(\_90)
end)

applyTheme(1)

\-- ============================================
\-- UPDATED STEAL LOGIC
\-- ============================================
local Players = game:GetService("Players")
local LP = Players.LocalPlayer
local getconnections = getconnections or (getgenv and getgenv().getconnections)

local STEAL_MODE_CFG = {
\[1\] = { threshold = 0.90, nearDist = 14 },
\[2\] = { threshold = 0.85, nearDist = 12 },
\[3\] = { threshold = 0.80, nearDist = 11 },
\[4\] = { threshold = 0.75, nearDist = 10 },
}
local isStealing = false
local stealConn = nil

local progressFill = Fill
local progressPct = Percent

local function setBar(p)
p = math.clamp(p or 0, 0, 1)
if progressFill then progressFill.Size = UDim2.new(p, 0, 1, 0) end
if progressPct then progressPct.Text = math.floor(p \* 100) .. "%" end
end

local function getStealHRP()
local c = LP.Character
return c and (c:FindFirstChild("HumanoidRootPart") or c:FindFirstChild("UpperTorso"))
end

local function isMyPlotByName(plotName)
local plots = workspace:FindFirstChild("Plots")
local plot = plots and plots:FindFirstChild(plotName)
if not plot then return false end
local sign = plot:FindFirstChild("PlotSign")
local yb = sign and sign:FindFirstChild("YourBase")
return yb and yb:IsA("BillboardGui") and yb.Enabled
end

local function getPromptPosition(prompt)
if not prompt then return nil end
local p = prompt.Parent
while p and p \~= workspace do
if p:IsA("BasePart") then return p.Position end
p = p.Parent
end
return nil
end

local function findNearestPrompt()
local hrp = getStealHRP()
if not hrp then return nil end
local plots = workspace:FindFirstChild("Plots")
if not plots then return nil end
local nearest, dist = nil, math.huge
for \_, plot in ipairs(plots:GetChildren()) do
if isMyPlotByName(plot.Name) then continue end
local pods = plot:FindFirstChild("AnimalPodiums")
if not pods then continue end
for \_, pod in ipairs(pods:GetChildren()) do
local base = pod:FindFirstChild("Base")
if not base then continue end
local spawn = base:FindFirstChild("Spawn")
if not spawn then continue end
local d = (spawn.Position - hrp.Position).Magnitude
if d <= Steal.StealRadius and d < dist then
local att = spawn:FindFirstChild("PromptAttachment")
if att then
for \_, p in ipairs(att:GetChildren()) do
if p:IsA("ProximityPrompt") and p.ActionText and p.ActionText:find("Steal") then
nearest, dist = p, d
end
end
end
end
end
end
return nearest
end

local function executeSteal(prompt)
if isStealing or not Steal.AutoStealEnabled then return end
if not Steal.Data\[prompt\] then
Steal.Data\[prompt\] = { hold = {}, trigger = {}, ready = true }
if getconnections then
for \_, c in ipairs(getconnections(prompt.PromptButtonHoldBegan) or {}) do
if c.Function then table.insert(Steal.Data\[prompt\].hold, c.Function) end
end
for \_, c in ipairs(getconnections(prompt.Triggered) or {}) do
if c.Function then table.insert(Steal.Data\[prompt\].trigger, c.Function) end
end
end
end
local data = Steal.Data\[prompt\]
if not data.ready then return end
data.ready = false
isStealing = true
task.spawn(function()
for \_, f in ipairs(data.hold) do pcall(f) end
end)
local cfg = STEAL_MODE_CFG\[Steal.Mode\] or STEAL_MODE_CFG\[4\]
local threshold = cfg.threshold
local nearDist = cfg.nearDist
local totalTime = tonumber(Steal.StealDuration) or 1.3
local timeToThreshold = totalTime \* threshold
local timeAfterThreshold = totalTime - timeToThreshold
local startTime = tick()
while tick() - startTime < timeToThreshold do
if not Steal.AutoStealEnabled then
isStealing = false; data.ready = true; setBar(0); return
end
setBar(math.clamp((tick() - startTime) / totalTime, 0, threshold))
task.wait()
end
setBar(threshold)
local stillNear = false
local hrp = getStealHRP()
if hrp then
local targetPos = getPromptPosition(prompt)
if targetPos and (targetPos - hrp.Position).Magnitude <= nearDist then
stillNear = true
end
end
if not stillNear then
local holdStart = tick()
while tick() - holdStart < 4 do
if not Steal.AutoStealEnabled then
isStealing = false; data.ready = true; setBar(0); return
end
setBar(threshold)
local hrp2 = getStealHRP()
if hrp2 then
local tp = getPromptPosition(prompt)
if tp and (tp - hrp2.Position).Magnitude <= nearDist then
stillNear = true
break
end
end
task.wait()
end
if not stillNear then
isStealing = false; data.ready = true; setBar(0); return
end
end
local resumeTime = tick()
while tick() - resumeTime < timeAfterThreshold do
if not Steal.AutoStealEnabled then
isStealing = false; data.ready = true; setBar(0); return
end
local fin = (tick() - resumeTime) / math.max(timeAfterThreshold, 0.01)
setBar(threshold + fin \* (1 - threshold))
task.wait()
end
setBar(1)
for \_, f in ipairs(data.trigger) do pcall(f) end
task.wait(0.05)
data.ready = true
isStealing = false
setBar(0)
end

function startAutoSteal()
if stealConn then return end
stealConn = RunService.Heartbeat:Connect(function()
if isStealing or not Steal.AutoStealEnabled then return end
local ok, prompt = pcall(findNearestPrompt)
if ok and prompt then
pcall(executeSteal, prompt)
end
end)
end

function stopAutoSteal()
if stealConn then
stealConn:Disconnect()
stealConn = nil
end
end

\-- ============================================
\-- INITIALIZE
\-- ============================================
if autoStealState then startAutoSteal() end
minimized = false
updateMinimize()

print("Capo X Nighthubv2 loaded successfully with updated steal logic.")