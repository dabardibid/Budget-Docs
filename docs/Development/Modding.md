---
slug: /docs/modding
title: Modding
description: This section should mostly cover everything about the game's open-source stuff, how to use it, modify and so on.
keywords: [docs, budget backrooms, mod, mod guide, budget docs]
---

![bb backrooms wiki modding banner](https://user-images.githubusercontent.com/32200281/232258762-98b0885e-b8b1-42fe-a3d9-62c8b9c530c2.png)
<div align="center">

# About this section

</div>

This section should mostly cover everything about the game's open-source stuff, how to use it, modify and so on.

Well, the game is open source so you're free to see what's hiding behind the blueprint stuff by [downloading the project](https://github.com/DavidJoacaRo/Budget-Backrooms/releases) (not the [binary release](https://github.com/DavidJoacaRo/Budget-Backrooms/releases)).

I hope you'll learn something and do something better for this game or, for your own game.

## ❓ Prerequisites

* Good PC running Windows.
* Basic computer literacy.
* Knowledge on how to use Unreal Engine.
    * UE 4.27.2 installed, if you use UE5 you're out of luck, good luck migrating I won't be assisting with that.
* Visual Studio 2022 (at the time of writing this, Visual Studio 2026 has NOT been tested with this project, I recommend on getting Visual Studio 2022 anyway by clicking [here](https://aka.ms/vs/17/release/vs_community.exe)).
    * Make sure the option **Game Development with C++** is ticked inside the Visual Studio Installer 🙏🙏🙏.


# 📁 Setting up the Project
---

:::info
**This guide is not foolproof. Make sure you have basic computer literacy before attempting this.**
:::


:::warning

*If you're having difficulties, [post an issue](https://github.com/DavidJoacaRo/Budget-Backrooms/issues) or [join the Discord server](https://discord.gg/WVuTB56ag4) and with your cooperation, we could further investigate the problem.*

:::
:::danger
* Before that, rename the `.uproject` to anything but not BudgetBackrooms, do this <ins>ONLY if you have more copies of the source code</ins> *(like one folder with the fork source code and other the original source code).*
    * There's this awkward bug in Unreal, that if you have the same name .uproject, shader recompilation will be re-triggered and we don't want to waste precious time.
        * Upon further testing you might also encounter compilation errors if renamed so it is a 50/50 situation, just separate the folders if none of the above work and keep the `.uproject` as it is.
:::

---

1. **[Clone the project using Git](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) (recommended if you want to pull latest changes more easily) or just download the source code as a `.zip` file and extract it.**
    * If downloading as a `.zip` and not using Git, you will encounter errors with DiscordRPC since it's a [submodule](https://github.blog/open-source/git/working-with-submodules/). You will find out how to fix this problem in the infobox below including the AMD FSR plugin installation steps.

2. **Make sure you've installed the required plugins inside the [.uproject](https://github.com/DavidJoacaRo/Budget-Backrooms/blob/main/BudgetBackrooms.uproject).**

:::warning

Make sure to download & install the Marketplace plugins first, and then open the project.

:::

:::info

* The **AMD FSR (AMD FidelityFX Super Resolution 1.0)** plugin can be found [here](https://gpuopen.com/learn/ue4-fsr/) since it's not available on the Unreal Marketplace.
    * *Further installation steps are mentioned on the website*.

* **DiscordRPC** can be installed by typing `git submodule update --init --recursive` in the game's root directory (usually where the `.uproject` is located)
    * If the project has been downloaded directly as a `.zip`, you can go to [LouisRaverdy/DiscordRPC](https://github.com/LouisRaverdy/DiscordRPC) and download the plugin from there.

:::


3. **You may be prompted to "rebuild" `BudgetBackrooms` when opening the project.**
* Encountering errors? (troubleshooting tips below)
    * 1. You could try right-clicking `BudgetBackrooms.uproject` and selecting **Generate Visual Studio project files** then, recompile Budget Backrooms inside Visual Studio (Build > **Build BudgetBackrooms**).
            * If the build didn't succeed anyway, try reading the log and see what went wrong, make sure the C++ Plugins such as **AdvancedSteamSessions** (and a few more) are installed inside the `Plugins` folder in the source code.
    * 2. If none of the above worked, make sure you got all the plugins installed as they are used in the project.
            * The paid plugin issue was solved [here](https://github.com/DavidJoacaRo/Budget-Backrooms/pull/28)
    * 3. As mentioned above, make sure you have Visual Studio 2019-2022 installed properly, since it's required to compile everything about C++ in the game, which is being used. Inside Visual Studio Installer, you can press **Modify** at your preferred VS installation, and then make sure the option **Game Development with C++** is ticked.
* If you don't encounter any (other) errors, proceed to rebuild without doing anything else.

4. Did you get the game's splash screen?
    * Yes
        * You are done, modify the heck of it (the game).

    * No
        * Backtrace your problem, and see what went wrong.
        * Revert some steps?
        * Still not working?
            * Ask for help by [making an issue](https://github.com/DavidJoacaRo/Budget-Backrooms/issues/new) or by [joining the Discord server](https://discord.gg/WVuTB56ag4).


