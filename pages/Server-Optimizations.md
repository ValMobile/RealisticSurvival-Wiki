<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
<details>
<summary>Table of Contents</summary>

- [1. Keeping an eye on performance](#1-keeping-an-eye-on-performance)
- [2. Choosing the right Server Software](#2-choosing-the-right-server-software)
- [3. Avoiding /reload](#3-avoiding-reload)
- [4. Slower Tick-rates](#4-slower-tick-rates)
- [5. Handling Cargo networks](#5-handling-cargo-networks)
- [6. Enabling Automatic updates](#6-enabling-automatic-updates)

</details>
<!-- END doctoc generated TOC please keep comment here to allow auto update -->

Realistic Survival is a really big plugin and therefore always raises questions about its performance.<br>
The plugin has been around since 2013 and has received many alterations and optimizations over the years. But depending on how you use this plugin, performance might differ.

This article should help you discover bottlenecks and limitations and guide you to optimize your server and your Realistic Survival configuration to run as smooth as possible.<br>
Here are some of the most important tips on how to optimize your Server or your Realistic Survival configuration:

## 1. Keeping an eye on performance
The most important aspect of Server-optimization is information.<br>
You need to know what to look for in order to improve performance, so here are some very important tools you should get familiar with:

### a) Server Profiling (/timings)
Spigot and Paper both come with their own profiler already. You can access this profiler by running `/timings` in chat.
These profilers provide insight into what your Server is struggling with, it can even break it down into each plugin you use and even the specific tasks of these plugins.

**Note:** Understanding a timings-report can be a difficult task.
Please refer to this [wiki article on spigotmc.org](https://www.spigotmc.org/wiki/timings/) for a general overview of how timings work.

But keep in mind that not every number in these reports is important, particularly "startup-tasks" can show up as red while they don't have any impact on performance since they
only run during the server's startup sequence.

### b) Plugin-based Server Profiling
In addition to your standard timings-tool, there are also some third-party tools which can help you and developers to track down where the lag is coming from code-wise.
We personally recommend [:zap: Spark by @Luck](https://www.spigotmc.org/resources/spark.57242/).
Reports from Spark have helped us tackle a few optimization problems and identify bottlenecks already, so it seems like a very useful asset for both, server owners and developers.

## 2. Choosing the right Server Software
Choosing the right Server Software plays an important role in Server-optimization.<br>
Since the discontinuation of CraftBukkit, [Spigot](https://www.spigotmc.org/) has become the standard Server software.
But there are countless alternatives and forks to choose from.
[Paper](https://papermc.io/) for example is a fork of Spigot and has proven itself to have slightly better performance than Spigot and also provides better and more detailed timings-reports.<br>
**Cargo networks** from Realistic Survival have been optimized to work best when using [Paper](https://papermc.io/).<br>
But there are countless other forks of Bukkit/Spigot out there which claim to also improve performance.
We suggest you to look into this yourself and make your own choice.

If you have control over your Server's Java version, try to choose the latest possible version of Java.

Once you have chosen a Server Software that you think is right for you, you should probably also dedicate some time to configuring this software.<br>
There have been many external guides on how to do that, so we will just link some of them here (*They are better at this than we are*):
* [Reducing Lag - A basic guide](https://www.spigotmc.org/wiki/reducing-lag/) (SpigotMC Wiki)
* [Server Optimization Guide](https://www.spigotmc.org/threads/guide-server-optimization%E2%9A%A1.283181/) (Posted by @Celbrimbor on the SpigotMC Forums)
* [Optimizing Java Garbage Collection](https://aikar.co/2018/07/02/tuning-the-jvm-g1gc-garbage-collector-flags-for-minecraft/) (@aikar's personal blog)

## 3. Avoiding /reload
**Do not use `/reload`. Ever.**<br>
Whenever you add a new plugin or edit a config file, restart your Server. Using `/reload` can cause huge [memory leaks](https://en.wikipedia.org/wiki/Memory_leak) that negatively impact your Server's performance. `/reload` is not safe to use and you should avoid it at all costs.

A lot of plugins are not meant to deal with reloads, and Realistic Survival is one of them. You should always restart your server instead.

## 4. Slower Tick-rates
Many Realistic Survival blocks execute code on a very regular basis, the default for this setting is set to run these tasks every 12 ticks (20 ticks = 1 second).<br>
You can increase this delay to slow down block-ticks which *might* help your server's performance.
However, you shouldn't set it too high, otherwise your players might complain about their machines running too slow.

You can configure this setting in your `plugins/RealisticSurvival/config.yml`. We recommend to only make small changes to the default value of 12 ticks when necessary.
```yaml
URID:
  custom-ticker-delay: 12
```

Similar to this setting, Realistic Survival regularly checks Player's armor to apply effects that come with wearing specific sets of armor.
The default setting for this task is set to 10 ticks (20 ticks = 1 second).<br>
You can also change this value when necessary.
```yaml
options:
  armor-update-interval: 10
```

## 5. Handling Cargo networks
Cargo networks are known to cause some performance drops depending on how they are set up.<br>
They have gone through many optimizations over the years but they can still cause a bit of trouble from time to time.

With the merge of [Pull Request #2106](https://github.com/RealisticSurvival/RealisticSurvival/pull/2106) Cargo networks have been drastically optimized to run best when using [Paper](https://papermc.io/). You can find more info about Server Software in section [2. Choosing the right Server Software](#2-choosing-the-right-server-software).

Here are two ways how you can limit cargo networks to prevent your players from making large networks that hurt your server's performance.

### a) Setting a maxmimum network size
You can set a maximum network size for cargo- and energy networks in your `plugins/RealisticSurvival/config.yml`.<br>
The default of 200 possible network members is very generous to players, decreasing this threshold will improve performance.<br>
Note that this limit corresponds to the amount of steps taken by the pathfinding algorithm that looks up possible network members, it does not correspond to the actual amount of nodes in your network!
```yaml
networks:
  max-size: 200
```

### b) Setting a cargo delay
Normally, cargo networks are treated like any other ticking block (see [Step 4](#4-slower-tick-rates)).<br>
But you can also make cargo managers run slower than other blocks.
This delay will make the cargo network skip the amount of ticks specified, a delay of 0 will make cargo networks tick on every run.
A delay of 1 will make networks only tick on every second run. A delay of 2 will make it skip 2 runs before it runs again, so it runs on every third run. And so on...

As this setting is multiplied by the tick-rate mentioned earlier, setting this too high can be a big disruption to your player's experience.<br>
We recommend setting it to 1 and only increase it when absolutely needed.
```yaml
networks:
  cargo-ticker-delay: 1
```

## 6. Enabling Automatic updates
Lastly, one of the most effective ways to optimize your performance is to keep automatic Realistic Survival updates enabled at all times!<br>
We regularly release patches, fixes and small performance optimizations and the plugin gets better (content- and performance-wise) with every newly released build.
You should always use the latest version, so we highly recommend you to enable `auto-updates` in your `plugins/RealisticSurvival/config.yml`.
```yaml
options:
  auto-update: true
```
