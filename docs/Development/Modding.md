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

* Decent PC running Windows 10 or better. (Windows 8/7 or older have not been tested but have fun in testing them for me :) )
    * At least an [Intel CPU from the last decade](https://en.wikipedia.org/wiki/List_of_Intel_processors#64-bit_processors:_Intel_64_(8th_and_9th_generation)_%E2%80%93_Coffee_Lake_microarchitecture) or an [AMD CPU from the last decade](https://en.wikipedia.org/wiki/List_of_AMD_processors#Zen_core_architecture_(2017%E2%80%93present)) is recommended to compile the shaders and at minimum run Unreal Engine.
    * A [Graphics Card](https://en.wikipedia.org/wiki/Graphics_card) or [Discrete GPU](https://en.wikipedia.org/wiki/Graphics_processing_unit) is recommended, almost required. How are you going to run the UE on your integrated graphics?
    * At least 16 GB of RAM but game has been usually compiled ([on my end at least](https://de.pcpartpicker.com/user/bardid/saved/#view=2vvprH)) at around 32 GB of RAM for headroom.
    * 32GB of storage and more, the repository itself is around 12 GB but with shaders and all that compiled stuff it is going to stack up. It is not a fixed size so just have enough free storage and headroom.
* Knowledge on how to use Unreal Engine
    * UE 4.27.2 installed, if you use UE5 you're out of luck, good luck migrating I won't be assisting with that.
* Visual Studio 2022
    * Make sure the option **Game Development with C++** is ticked inside the Visual Studio Installer 🙏🙏🙏.
:::danger
At the time of writing this, Visual Studio 2026 does NOT work with this project because it's in Unreal Engine 4.27.2 and thus the Visual Studio plugin has not been updated to work with it (and most likely won't be updated for UE4 any time soon), I recommend on getting Visual Studio 2022  by clicking [here](https://aka.ms/vs/17/release/vs_community.exe)
:::

# 📁 Setting up the Project
---

:::info
**This guide is not foolproof. Make sure you have basic computer literacy before attempting this.**
:::


:::warning

*If you're having difficulties, [post an issue](https://github.com/DavidJoacaRo/Budget-Backrooms/issues) or [join the Discord server](https://discord.gg/WVuTB56ag4) and with your cooperation, we could further investigate the problem.*

:::
:::danger
* In the case of having multiple copies of the project, do not keep the same `.uproject` filename and project name everywhere (edited inside the `.uproject` file) since Unreal Engine geeks out and will most likely trigger shader recompilation. And thus, wasting precious time.
:::

---

1. **[Clone the project using Git](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) (recommended if you want to pull latest changes more easily) or just download the source code as a `.zip` file and extract it.**
    * If downloading as a `.zip` and not using Git, you will encounter errors with DiscordRPC since it's a [submodule](https://github.blog/open-source/git/working-with-submodules/). You will find out how to fix this problem in the infobox below including the AMD FSR plugin installation steps.

2. **Make sure you've installed any additional plugins required inside the [.uproject](https://github.com/DavidJoacaRo/Budget-Backrooms/blob/main/BudgetBackrooms.uproject).** (Most of them are bundled with the project anyway)

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
    * 2. If none of the above worked, make sure you got all the plugins installed as they are used in the project.
            * The paid plugin issue was solved [here](https://github.com/DavidJoacaRo/Budget-Backrooms/pull/28).
    * 3. As mentioned above, make sure you have Visual Studio 2019-2022 installed properly, since it's required to compile everything about C++ in the game, which is being used. Inside Visual Studio Installer, you can press **Modify** at your preferred VS installation, and then make sure the option **Game Development with C++** is ticked.
* If you don't encounter any (other) errors, proceed to rebuild without doing anything else.

4. Did you get the game's splash screen?
    * Yes
        * You are done, feel free to explore around.

    * No
        * Backtrace your problem, and see what went wrong.
        * Revert some steps?
        * Still not working?
            * Ask for help by [making an issue](https://github.com/DavidJoacaRo/Budget-Backrooms/issues/new) or by [joining the Discord server](https://discord.gg/WVuTB56ag4).


