## Conerals 更新日志

### 1.0.0

**1.0.0 — Canary**
- 创建 Visual Studio 解决方案 `ConeralsOnWebUI`
- C++ DLL + C# WinUI 3 架构

**1.0.0 — Beta**
- 解决 WinUI 3 在 Windows 10 上 `0x80070005` 权限错误，切换为非打包模式
- 配置 `/utf-8` 编译选项，启用 C++14 标准
- 解决 `Conerals.Core.dll` 找不到、`copy` 命令失败
- 解决 `EntryPointNotFoundException`：显式 `EntryPoint`
- 验证 P/Invoke

**1.0.0**
- 项目骨架可用，单机可运行

---

### 1.0.1

- 修复 AI 头文件里 `(movement){...}` 报错
- 修复光标越界

---

### 1.1.0

**1.1.0 — Canary**
- 移植 `mainGenerals.h`：`block`、`movement`、`MakeGeneralsMap`、`FloodFillTheMap`、`Ask`
- 导出 `Conerals_InitGame`、`Conerals_GetMapSnapshot`
- C# 用 `Canvas` + `Rectangle` 渲染 10×10 地图

**1.1.0 — Beta**
- 地图居中显示
- 格子尺寸随地图大小动态调整
- 修复数字被格子遮挡

**1.1.0**
- 地图生成稳定，渲染正常

---

### 1.1.1
- 修复地图边界连通性检查
- 修复 `MakeGeneralsMap` 循环次数上限

---

### 1.2.0

**1.2.0 — Canary**
- 导出 `Conerals_HumanMove`
- C# 方向键驱动
- 黄色光标显示当前选中格子

**1.2.0 — Beta**
- `RootGrid.PreviewKeyDown` 解决空格被 WinUI 吞掉

**1.2.0**
- 键盘操作稳定

---

### 1.2.1
- 修复光标在己方格子外时方向键无效

---

### 1.3.0

**1.3.0 — Canary**
- 导出 `Conerals_AdvanceTurn`
- 把原 `Generals()` 循环拆成 `ApplyMove` / `CheckDeath` / `AddArmiesByTurn`

**1.3.0 — Beta**
- 修复回合结算顺序
- 修复加兵时机

**1.3.0**
- 回合推进稳定

---

### 1.4.0

**1.4.0 — Canary**
- `Conerals_GetMapSnapshot` 内部走 `Ask`，实现九宫格视野遮挡
- C# 渲染区分 `'?'`、`'B'`、`'M'`、`'K'`、`'C'`、`'L'`

**1.4.0 — Beta**
- 修复视野边界
- 修复不可见格子颜色

**1.4.0**
- 视野系统稳定

---

### 1.5.0

**1.5.0 — Canary**
- 静态 include 所有 AI 头文件，`GetAIMove` 按名字分发
- 可选 AI：人机、Explorer、DeepSeek、example1、example2、Developer、Cmyan

**1.5.0 — Beta**
- 修复 `GetAIMove` 前未调 `AI::Init()` 导致 AI 跨玩家状态污染
- 修复 `feiwu.h`、`ChatGPT.h` 等 AI 头文件语法不兼容
- 修复 AI 被灭后不消失

**1.5.0**
- 人类 vs AI 完整对局可玩

---

### 1.5.1
- 修复 AI 返回越界坐标被 `ApplyMove` 静默拦截
- 修复 `Cmyan` 与 `DeepSeek` 状态残留

---

### 1.6.0

**1.6.0 — Canary**
- 侧栏 `NavigationView`：游戏 / 设置
- `StartPage`：玩家 1 / 玩家 2 下拉框选 AI
- `SettingsPage`：地图尺寸（10×10 / 20×20 / 30×30）

**1.6.0 — Beta**
- 引入 `CommunityToolkit.WinUI.Controls.SettingsControls` 美化设置卡片

**1.6.0**
- 开始页与设置页稳定

---

### 1.7.0

**1.7.0 — Canary**
- 每回合检查胜负，弹出 `ContentDialog`
- 左上角"返回"按钮回开始页

**1.7.0 — Beta**
- 人类赢显示"胜利"，AI 赢显示"失败"
- 结束弹窗只有一个"确定"按钮

**1.7.0**
- 游戏结束逻辑稳定

---

### 1.8.0

**1.8.0 — Canary**
- 设置页新增自动推进开关和回合间隔滑块
- `DispatcherTimer` 每 N 毫秒调 `AdvanceTurn`
- 用 `AppConfig.cs` 保存到 `%LOCALAPPDATA%`

**1.8.0 — Beta**
- 自动推进关闭时"回合间隔"卡片置灰
- 修复 `ApplicationData.Current` 在非打包模式不可用

**1.8.0**
- 自动推进与配置持久化稳定

---

### 1.9.0

**1.9.0 — Canary**
- 设置页底部新增法律信息分组
- 设置页底部新增恢复默认设置按钮

**1.9.0 — Beta**
- 接入 `CommunityToolkit.WinUI.UI.Controls.Markdown`
- 用 `MarkdownTextBlock` 渲染协议文本

**1.9.0**
- 法律信息与恢复默认稳定

---

### 1.10.0

**1.10.0 — Canary**
- 设置页新增外观 / 主题：跟随系统 / 浅色 / 深色
- 每个 `Page` 应用 `RequestedTheme`

**1.10.0 — Beta**
- `ContentDialog` 显式设置 `RequestedTheme`
- 修复深色模式下部分区域不跟随

**1.10.0**
- 主题切换稳定

---

### 2.0.0

**2.0.0 — Canary**
- 顶栏显示玩家名字 + 色点 + 回合数
- "返回"改为"退出"，点击弹确认对话框

**2.0.0 — Beta**
- 游戏页进入时隐藏侧栏，退出时恢复

**2.0.0**
- 顶栏改进与退出稳定

---

### 2.1.0

**2.1.0 — Canary**
- 加兵频率加快：国王/城市每 1 回合 +1，领土每 25 回合 +1
- T 键回大本营
- 空格 / 回车推进回合

**2.1.0 — Beta**
- 修复回大本营找不到国王的情况

**2.1.0**
- 游戏节奏稳定

---

### 2.2.0

**2.2.0 — Canary**
- 窗口图标：`appicon.ico` 设置到 `AppWindow`
- exe 图标：`.csproj` 的 `ApplicationIcon`

**2.2.0 — Beta**
- 侧栏游戏图标：`Segoe MDL2 Assets` 手柄字符
- 窗口默认尺寸 1200×800

**2.2.0**
- 图标与窗口稳定

---

### 2.3.0

**2.3.0 — Canary**
- 游戏页顶栏新增接管控制按钮
- 设置页新增玩家人数（2 / 3 / 4）
- 开始页动态显示 3、4 号位下拉框
- 顶栏显示所有玩家的名字 + 颜色点

**2.3.0 — Beta**
- 接管后人类可操作该玩家，接管一次后按钮永久置灰
- 死亡后显示"（已死亡）"
- 修复接管后再切换时 AI 下线
- 修复接管后自己死了不结束（加 `IsPlayerDead(_humanId)` 判断）

**2.3.0**
- 接管控制与多人对战稳定

---

### 2.4.0

**2.4.0 — Canary**
- 修复 `StartPage.xaml.cs` 与 `SettingsPage.xaml.cs` 类名错乱导致的满屏二义性
- 修复 `GamePage.xaml.cs` 字段区语法错误导致的 40 条级联错误

**2.4.0 — Beta**
- 修复 `LegalPage.xaml.cs` 未创建但被引用
- 修复 `MainWindow.Current` 与 `Window.Current` 重名冲突
- 关闭 `PublishTrimmed` 和 `PublishReadyToRun`
- 修复发布产物缺 `Conerals.Core.dll`
- 修复 `resources.pri` 未生成导致 `0xc000027b` 启动崩溃
- 移除 `csproj` 残留 MSIX 配置
- ProcMon 追踪到崩在 `HKLM\Software\Microsoft\WinUI\XAML` 缺失 + `combase.dll`

**2.4.0**
- 修复 `sdk-manifests\8.0.100.bak` 导致 `dotnet --info` 抛 `System.FormatException`
- 修复 .NET SDK 与 Desktop Runtime 版本不匹配导致 `DotNetMSBuildSdkResolver` 加载失败
- 修复 `DOTNET_ROOT` 环境变量未设置
- 发布产物在干净电脑上可运行

---

### 3.0.0 — 联机初版（Canary）

- 局域网直连
- 新增 `network_server.h` / `network_client.h`
- 新增联机相关导出接口
- 新增 `NetworkPage`
- 侧边栏新增联机入口

---

### 3.0.1 — 联机页面重构（Canary）

- 本机模式卡片
- 服务器端 / 游戏端分离
- 连接失败显式提示
- 准备按钮

---

### 3.0.2 — 联机二级页面（Canary）

- 玩家列表
- 准备完成
- 侧栏收起
- 返回按钮
- 菜单改名

---

### 3.1.0 — 游戏内交互改进（Canary）

- 延迟范围 10~2000ms
- 点击移动
- 暂停按钮

---

### 3.1.1 — 外观改进（Canary）

- 取消格子边框开关
- 文本框裁剪修复

---

### 3.2.0 — 性能优化（Canary）

- 大地图渲染优化

---

### 3.2.1 — 触摸屏与缓存修复（Canary）

- 触摸屏卡死
- `AppConfig` 缓存 bug
- 联机状态重置
