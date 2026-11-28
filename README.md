# Minecraft Hosting — Complete User Guide

A GitHub Actions-powered Minecraft Java Edition hosting project with a web-based dashboard, automated server installation, server management, and public connectivity.

This guide explains everything from setting up the project for the first time to managing your Minecraft server directly from the dashboard.

Whether you want to create a Vanilla Survival server, a Forge modded server, a Paper server, or experiment with other Minecraft server software, this guide will help you get started.

---

# TABLE OF CONTENTS

1. Project Overview
2. Requirements
3. Getting Started from Zero
4. Starting the Hosting Workflow
5. Accessing the Dashboard
6. Dashboard Overview
7. Installing Your First Minecraft Server
8. Starting and Stopping Your Server
9. Managing Players and Permissions
10. Managing Your Minecraft World
11. Console Commands
12. Server Performance and RAM
13. Mods, Plugins and Compatibility
14. Server Backups and Data
15. Troubleshooting and Frequently Asked Questions
16. Security and Important Information

---

# 1. PROJECT OVERVIEW

This project allows you to create and manage a Minecraft Java Edition server through a web-based control panel.

Instead of manually installing Java, downloading server files, and configuring networking, the project automates much of the setup process.

## Main Features

- Web-based Minecraft management dashboard.
- Automated Minecraft server installation.
- Support for multiple Minecraft server software options.
- Configurable Java version.
- Configurable RAM allocation.
- Public Minecraft connectivity through Bore.
- Public dashboard access through Cloudflare Quick Tunnel.
- Server console access.
- Server startup and shutdown controls.
- Live server status and resource information where supported.

## Supported Server Software

| Software | Description |
|---|---|
| Vanilla | Official Minecraft server |
| Paper | Performance-oriented server with plugin support |
| Fabric | Lightweight modding platform |
| Forge | Modded Minecraft |
| NeoForge | Modern modding platform |
| Velocity | Minecraft proxy |
| BungeeCord | Minecraft network proxy |
| Folia | Region-based Paper fork |
| Quilt | Alternative modding platform |
| Arclight | Hybrid mod and plugin environment |

**Important:** Velocity and BungeeCord are proxy software. They require backend Minecraft servers and are not standalone Survival servers.

---

# 2. REQUIREMENTS

Before using the project, make sure you have:

- A GitHub account.
- A web browser.
- Minecraft Java Edition.
- An internet connection.
- A compatible Minecraft client.
- Access to the repository containing the hosting workflow.

You do not need to install Java or Minecraft server software manually on your own computer.

---

# 3. GETTING STARTED FROM ZERO

## STEP 1 — Fork the Repository

1. Open the GitHub repository containing the Minecraft Hosting project.
2. Log into your GitHub account.
3. Find the **Fork** button near the upper-right corner of the page.
4. Click **Fork**.
5. Select your personal GitHub account.
6. If necessary, choose a repository name.
7. Click **Create fork**.
8. Wait until GitHub finishes copying the repository.

You should now be inside your own copy of the project.

## STEP 2 — Enable GitHub Actions

1. Open your forked repository.
2. Navigate to the **Actions** tab.
3. If GitHub displays a message asking you to enable workflows, enable them.
4. Find the hosting workflow in the left sidebar.
5. Make sure the workflow is available to run.

Depending on your repository settings, you may need to allow the workflow to access the repository permissions it requires.

## STEP 3 — Prepare Your First Hosting Session

1. Open the **Actions** tab.
2. Select the Minecraft hosting workflow.
3. Find the **Run workflow** button.
4. Click it.
5. Review the available configuration options.

The current workflow provides:

| Option | Available configuration |
|---|---|
| Session Duration | 60–300 minutes |
| Java Version | Java 8, 17, 21, 25 |

The default session duration is 300 minutes.

The default Java version is Java 21.

## STEP 4 — Launch the Workflow

1. Select the session duration.
2. Select your Java version.
3. Click **Run workflow**.
4. Wait for GitHub to create the runner.
5. Open the newly created workflow run.
6. Select the running job to inspect its logs.

The workflow now prepares the hosting environment.

**Do not cancel the workflow while you want your hosting session to remain available.**

## STEP 5 — Find Your Dashboard Credentials

After the setup process completes, inspect the workflow logs.

Find the following information:

- `DASHBOARD URL`
- `OWNER PASSWORD`
- `MINECRAFT JAVA SERVER ADDRESS`

Copy the values somewhere secure.

The dashboard URL opens your web control panel.

The owner password allows you to log in with the default username:

`owner`

The Minecraft address is used by Minecraft Java Edition to connect to your server after installation.

Never publish your password or share logs containing private credentials.

---

# 4. ACCESSING THE DASHBOARD

## STEP 1 — Open the Dashboard

1. Open your browser.
2. Paste the `DASHBOARD URL` from the workflow logs into the address bar.
3. Press Enter.
4. Wait for the dashboard to load.

If the page does not load, make sure the GitHub Actions workflow is still running and the Cloudflare tunnel is active.

## STEP 2 — Log In

1. Find the login form.
2. Enter the username:

   `owner`

3. Enter the `OWNER PASSWORD` from the workflow logs.
4. Submit the login form.
5. Wait for the dashboard to open.

You should now have access to the hosting control panel.

## STEP 3 — Understand the Dashboard

The dashboard is your central place for managing your Minecraft server.

Depending on the available dashboard version, you may see information such as:

- Server status.
- Installed Minecraft version.
- Selected server software.
- Memory usage.
- CPU usage.
- Uptime.
- Console output.
- Server management controls.
- Installation options.

### Understanding Server Status

| Status | Meaning |
|---|---|
| RUNNING | The server process is running |
| STOPPED | The server is not running |
| STARTING | The server is starting |
| STOPPING | The server is shutting down |
| CRASHED | The server process has unexpectedly stopped |
| INSTALLING | The installation process is running |

The exact status names depend on the dashboard implementation.

---

# 5. INSTALLING YOUR FIRST MINECRAFT SERVER

This is one of the most important parts of the project.

Follow every step carefully.

## STEP 1 — Open the Installation Wizard

After logging in:

1. Locate the server installation section.
2. Open the installation wizard.
3. Wait for the available configuration options to load.

Do not attempt to start a server before completing the installation.

## STEP 2 — Select Your Minecraft Version

Choose the Minecraft version you want.

Examples:

- 1.16.5
- 1.18.2
- 1.19.4
- 1.20.1
- 1.21.x
- 26.3

The exact versions available depend on the installer.

**Recommendation:** If you are creating a modded server, choose your Minecraft version before selecting your mods. Not every mod supports every Minecraft version.

## STEP 3 — Select Your Server Software

Choose the software you want to install.

### Vanilla

Choose Vanilla if you want the official Minecraft server without additional modding or plugin platforms.

### Paper

Choose Paper if you want a server optimized for multiplayer and plugin support.

### Fabric

Choose Fabric if you want to install Fabric-compatible mods.

### Forge

Choose Forge if you want a traditional modded Minecraft experience.

### NeoForge

Choose NeoForge for modpacks and mods designed for its ecosystem.

### Folia

Choose Folia for compatible region-threaded server setups. Check plugin compatibility carefully.

### Quilt

Choose Quilt if your selected mods support it.

### Arclight

Choose Arclight if you specifically need a compatible hybrid mod-and-plugin environment.

### Velocity and BungeeCord

Choose these only when creating a proxy for a Minecraft network.

They require one or more backend Minecraft servers.

## STEP 4 — Choose the Loader or Release

Some server software requires an additional loader or release selection.

For example, Forge and Fabric may require you to select a compatible loader version.

Make sure that:

- The loader supports your Minecraft version.
- Your mods support the selected loader.
- The Java version is compatible.

## STEP 5 — Configure Server RAM

Choose the amount of RAM you want to allocate.

The dashboard supports selections between 2 GB and 12 GB.

Suggested starting points:

| Server type | Suggested starting allocation |
|---|---:|
| Small Vanilla | 2–3 GB |
| Small Paper | 2–4 GB |
| Fabric | 3–5 GB |
| Forge | 4–8 GB |
| Large modpack | Depends on the modpack |

These are starting suggestions, not guarantees. Actual memory requirements depend on the Minecraft version, mods, player count, and available runner resources.

## STEP 6 — Confirm the Installation

1. Review your selected Minecraft version.
2. Review your server software.
3. Check the loader version if applicable.
4. Review the RAM allocation.
5. Start the installation.
6. Wait for the installer to finish.

Do not refresh or close the dashboard while the installation is running unless the application supports safely continuing the operation.

## STEP 7 — Verify the Installation

After installation:

1. Open the server information section.
2. Check that the selected Minecraft version is correct.
3. Check the server software.
4. Inspect the console for installation errors.
5. Confirm that the installation process has completed.

You can now start the server.

---

# 6. STARTING AND STOPPING YOUR SERVER

## How to Start the Server

1. Open the dashboard.
2. Locate the server control section.
3. Click **Start**.
4. Wait for the server process to launch.
5. Open the console.
6. Watch the startup messages.

A successful Minecraft server startup normally ends with a message similar to:

`Done (...)! For help, type "help"`

Once the server is ready, try connecting using your Minecraft address.

## How to Stop the Server

1. Open the dashboard.
2. Find the server control section.
3. Click **Stop**.
4. Wait for the server to finish shutting down.
5. Check the console for the shutdown confirmation.

Avoid forcibly terminating the process unless the server is completely unresponsive.

A graceful shutdown gives Minecraft an opportunity to save world data.

## How to Restart the Server

If the dashboard provides a Restart control, use it.

Otherwise:

1. Stop the server.
2. Wait until the process has completely stopped.
3. Click Start.
4. Wait for Minecraft to finish loading.

Do not start a second server process while the previous one is still running.

---

# 7. CONNECTING TO YOUR MINECRAFT SERVER

## Java Edition

1. Launch Minecraft Java Edition.
2. Select Multiplayer.
3. Click Add Server.
4. Enter a name, such as `My Minecraft Server`.
5. Paste the `MINECRAFT JAVA SERVER ADDRESS` from the workflow logs.
6. Click Done.
7. Select your server.
8. Click Join Server.

Make sure you use the Minecraft address, not the dashboard URL.

## Modded Minecraft

For Forge, Fabric, NeoForge, or Quilt servers:

1. Install the matching mod loader in your Minecraft launcher.
2. Select the same Minecraft version as the server.
3. Install the required client-side and shared mods.
4. Make sure the mod versions are compatible.
5. Launch Minecraft.
6. Connect to the server.

A client using the wrong mod loader or incompatible mods may be rejected.

---

# 8. MANAGING PLAYERS AND PERMISSIONS

Minecraft server administration is often performed through the server console.

The following commands are standard Minecraft server commands. Enter them without the leading `/` when using a server console.

## How to Give Yourself OP

OP gives a player operator privileges.

1. Open the dashboard.
2. Open the server console.
3. Wait until the server is running.
4. Enter:

`op YourMinecraftUsername`

5. Press Enter.
6. Check the console for confirmation.
7. Reconnect if necessary.

Replace `YourMinecraftUsername` with your actual Minecraft username.

Example:

`op Steve`

You should now have operator permissions.

## How to Remove OP

Enter:

`deop YourMinecraftUsername`

Example:

`deop Steve`

## How to Change a Player's Game Mode

Creative:

`gamemode creative PlayerName`

Survival:

`gamemode survival PlayerName`

Adventure:

`gamemode adventure PlayerName`

Spectator:

`gamemode spectator PlayerName`

## How to Teleport Players

Teleport yourself to another player:

`tp YourName OtherPlayer`

Teleport one player to another:

`tp Player1 Player2`

Teleport a player to coordinates:

`tp PlayerName 100 80 -200`

## How to Kick a Player

`kick PlayerName Reason`

Example:

`kick Steve Please reconnect later`

## How to Ban a Player

`ban PlayerName Reason`

Example:

`ban Steve Breaking the server rules`

## How to Unban a Player

`pardon PlayerName`

## How to Manage the Whitelist

Enable whitelist:

`whitelist on`

Disable whitelist:

`whitelist off`

Add a player:

`whitelist add PlayerName`

Remove a player:

`whitelist remove PlayerName`

Display whitelist:

`whitelist list`

## How to See Online Players

`list`

## How to Change the Server Difficulty

`difficulty peaceful`

`difficulty easy`

`difficulty normal`

`difficulty hard`

## How to Change the Time

`time set day`

`time set night`

`time set noon`

## How to Change the Weather

`weather clear`

`weather rain`

`weather thunder`

## How to Change the World Spawn

`setworldspawn`

## How to Give Yourself Items

`give YourName minecraft:diamond 64`

Replace the player name and item as needed.

## How to Stop the Server Safely

`stop`

This command asks Minecraft to shut down gracefully.

---

# 9. MANAGING YOUR MINECRAFT WORLD

## How to Change the World Seed

The world seed is normally selected when the world is first generated.

Changing the seed in a configuration file does not automatically regenerate an existing world.

To use a different seed, you generally need to create a new world.

**Important:** Back up the existing world before replacing or deleting it.

## How to Reset Your World

1. Stop the Minecraft server.
2. Back up the current world.
3. Identify the world directory.
4. Rename or remove the old world only after confirming the backup exists.
5. Configure the new world settings.
6. Start the server.

Minecraft will generate a new world if the configured world directory does not contain an existing world.

The exact world directory depends on the server configuration.

## How to Change the World Difficulty

Use the console:

`difficulty hard`

You can also configure the default difficulty through `server.properties`.

## How to Enable or Disable PvP

Open `server.properties` and locate:

`pvp=true`

Set it to:

`pvp=false`

Restart the server if required for the change to take effect.

## How to Enable Command Blocks

Open `server.properties`.

Find:

`enable-command-block=false`

Change it to:

`enable-command-block=true`

Restart the server.

## How to Change the Maximum Player Count

Open `server.properties`.

Find:

`max-players=20`

Change the value to your desired player limit.

The actual number of players supported depends on server resources.

---

# 10. CONSOLE COMMANDS

The server console is one of the most useful tools available to a Minecraft administrator.

It allows you to:

- Give OP.
- Remove OP.
- Change game modes.
- Teleport players.
- Ban and unban players.
- Manage the whitelist.
- Change world settings.
- Inspect server messages.
- Stop the server safely.

### Important Console Rule

When entering commands directly into the server console, normally omit the `/`.

For example:

Correct:

`op Steve`

Usually unnecessary in console:

`/op Steve`

---

# 11. SERVER PERFORMANCE AND RAM

## Understanding RAM Usage

The dashboard may display information such as:

`1.32 GB / 5.00 GB`

This means the server is currently using approximately 1.32 GB out of the configured 5 GB allocation.

Memory usage naturally changes as the server loads chunks, players join, and mods perform tasks.

## Understanding CPU Usage

CPU usage indicates how much processing work the server is performing.

High CPU usage may occur during:

- World generation.
- Chunk loading.
- Large mob farms.
- Heavy mod activity.
- Multiple players exploring new areas.

Low CPU usage does not automatically guarantee perfect server performance.

## Understanding TPS

TPS means Ticks Per Second.

Minecraft normally targets 20 TPS.

| TPS | General interpretation |
|---|---|
| 20 | Ideal |
| 18–19 | Slight performance issues |
| 15–17 | Noticeable slowdown |
| 10–14 | Significant lag |
| Below 10 | Severe performance problems |

These are general guidelines.

If the dashboard shows `N/A`, it may not currently have access to a valid TPS metric.

## How to Reduce Server Lag

Try the following:

1. Reduce unnecessary entities.
2. Avoid excessive redstone machines.
3. Reduce the number of loaded chunks.
4. Check for poorly optimized mods.
5. Avoid running unnecessary plugins.
6. Monitor memory usage.
7. Investigate console warnings.
8. Reduce the workload from large farms.

## How to Reduce Client-Side Lag

If the server is working correctly but Minecraft still stutters:

- Reduce Render Distance.
- Reduce Simulation Distance.
- Set Graphics to Fast.
- Disable unnecessary particles.
- Reduce entity distance.
- Close background applications.
- Use a compatible Minecraft version and launcher.

Remember: server lag and client FPS problems are different issues.

---

# 12. MODS, PLUGINS AND COMPATIBILITY

## How to Install Mods

For a modded server:

1. Stop the server.
2. Open the appropriate server files location if the dashboard provides file management.
3. Locate the `mods` directory.
4. Upload or place the required server-compatible mod files.
5. Check that the mods support your Minecraft version.
6. Check that the mods support your loader.
7. Start the server.
8. Inspect the console for errors.

If your dashboard does not provide file uploads, use the project's supported installation or file-management method.

## How to Install Plugins

For Paper and other compatible server software:

1. Stop the server.
2. Locate the `plugins` directory.
3. Add the compatible plugin JAR files using the supported file-management method.
4. Start the server.
5. Inspect the console for plugin loading errors.

Not all server software supports plugins.

Forge and Fabric do not automatically support Bukkit or Paper plugins.

## Why Is a Mod Missing?

Possible reasons:

- The mod was installed only on the client.
- The mod was placed in the wrong directory.
- The mod version is incompatible.
- The server was not restarted.
- The mod requires another dependency.

## Why Does the Server Reject My Modded Client?

Check that your client and server use compatible:

- Minecraft versions.
- Mod loaders.
- Mod versions.
- Required dependencies.

Some mods must be installed on both the server and client.

---

# 13. SERVER BACKUPS AND DATA

## Why Are Backups Important?

A Minecraft world can contain hundreds of hours of progress.

Always back up important data before:

- Updating Minecraft.
- Updating mods.
- Changing server software.
- Replacing the world.
- Installing experimental plugins.
- Making major configuration changes.

## How to Create a Manual World Backup

If the dashboard provides backup functionality, use it.

Otherwise, stop the server and copy the world directory using the project's supported storage method.

A backup should include all required world data, not just one region file.

## Does My World Automatically Persist Between Workflow Runs?

Not automatically.

GitHub Actions runners are temporary. Files created only on the runner can disappear when the job ends.

Your project must implement persistent storage, backup, and restoration if worlds are expected to survive between sessions.

---

# 14. TROUBLESHOOTING AND FREQUENTLY ASKED QUESTIONS

## DASHBOARD AND INSTALLATION

### Q1. I opened the dashboard, but it does not load. What should I do?

Check that the workflow is still running.

Then:

1. Open GitHub Actions.
2. Select the active workflow run.
3. Inspect the logs.
4. Look for the dashboard startup message.
5. Check whether Cloudflare Quick Tunnel was successfully created.
6. Copy the current dashboard URL again.

### Q2. I entered my password, but login does not work.

Check that you are using:

- Username: `owner`
- The correct password from the current workflow run.

Make sure you are not using credentials from an older session.

### Q3. The dashboard loads, but the server is not installed. Why?

Opening the dashboard does not necessarily install Minecraft automatically.

You must complete the installation wizard before starting the server.

### Q4. The installation wizard is not responding.

Try refreshing the dashboard once.

If the issue continues, inspect the workflow and application logs.

Do not repeatedly submit installation requests while a previous installation may still be running.

### Q5. The installation failed. What should I do?

Inspect the console or installer output.

Look for download errors, unsupported versions, missing dependencies, and permission errors.

Verify the selected Minecraft version, server software, and Java compatibility.

### Q6. The installation is taking a long time. Is that normal?

It can be normal for larger installations, particularly modded server software.

However, if there is no progress and the logs show repeated errors, investigate the first error message.

### Q7. Can I install another server after installing one?

That depends on the dashboard's installation and storage implementation.

Do not overwrite an existing world or installation without backing it up first.

### Q8. Can I change server software after installation?

Changing software may require a new installation.

For example, moving from Vanilla to Forge is not simply a Java version change.

Back up your world before changing software.

---

## SERVER STARTUP AND CRASHES

### Q9. My server refuses to start. What should I check?

Open the dashboard console.

Look for the first error that appears during startup.

Check:

- Minecraft version.
- Java version.
- Server software.
- Loader compatibility.
- RAM allocation.
- Missing dependencies.
- Invalid configuration files.

### Q10. My server crashed. How can I find out why?

1. Open the dashboard.
2. Open the console or available log viewer.
3. Scroll to the last messages before the crash.
4. Look for `Exception`, `ERROR`, `Caused by`, or `Crash Report`.
5. Identify the first meaningful error.
6. Check whether a mod, plugin, or configuration caused it.

Do not rely only on the final line saying that the process exited.

### Q11. The server says OutOfMemoryError. What does that mean?

The Java process could not allocate the memory it needed.

Possible solutions:

- Review the RAM allocation.
- Remove unnecessary mods.
- Reduce the server workload.
- Check whether the runner has enough available memory.

Increasing the configured allocation only helps if the underlying runner has enough memory.

### Q12. The server crashes immediately after I install a mod.

The mod may be incompatible or missing a dependency.

Stop the server, remove or update the suspected mod, and check its required Minecraft and loader versions.

### Q13. My server is stuck on Starting.

Check whether the console is still producing new messages.

Modded servers can take longer to load.

If the process has stopped producing output, inspect the last error and determine whether the server is actually stuck or still performing work.

### Q14. I see UnsupportedClassVersionError. What should I do?

This usually indicates a Java compatibility problem.

Choose a Java version compatible with your Minecraft version and server software.

### Q15. I see Address already in use. What does it mean?

Another process may already be using the requested local port.

Check whether an old server process is still running before starting another instance.

### Q16. The server starts and then immediately stops.

Inspect the console for:

- Invalid configuration.
- Missing dependencies.
- Incorrect Java.
- Failed world loading.
- Insufficient memory.
- A mod or plugin crash.

### Q17. The server says Done, but nobody can join.

A successful startup does not guarantee that the public tunnel is working.

Check that Bore is active and that you are using the correct public Minecraft address.

---

## OP AND PLAYER ADMINISTRATION

### Q18. How do I give myself OP?

Open the dashboard console and enter:

`op YourMinecraftUsername`

Replace the placeholder with your actual Minecraft username.

### Q19. I entered the OP command, but I still cannot use commands.

Check:

1. Did you enter the correct Minecraft username?
2. Did the console confirm the command?
3. Are you connected to the correct server?
4. Are you using the account you gave OP to?
5. Does your server use a permissions plugin that changes command permissions?

### Q20. How do I remove someone's OP?

`deop PlayerName`

### Q21. How do I make myself Creative?

`gamemode creative YourMinecraftUsername`

### Q22. How do I return to Survival?

`gamemode survival YourMinecraftUsername`

### Q23. How do I ban someone?

`ban PlayerName Reason`

### Q24. How do I unban someone?

`pardon PlayerName`

### Q25. How do I kick someone?

`kick PlayerName Reason`

### Q26. How do I teleport to another player?

`tp YourName OtherPlayer`

### Q27. How do I see who is online?

`list`

### Q28. How do I enable the whitelist?

`whitelist on`

### Q29. How do I add someone to the whitelist?

`whitelist add PlayerName`

### Q30. How do I remove someone from the whitelist?

`whitelist remove PlayerName`

### Q31. How do I change the maximum number of players?

Edit the `max-players` value in `server.properties`, then restart the server if necessary.

### Q32. Can I use commands without being OP?

Some commands are available to ordinary players, but administrative commands normally require appropriate permissions.

---

## WORLD AND CONFIGURATION

### Q33. How do I reset my world?

Stop the server, create a backup, and replace the world directory using the supported storage method.

Never delete the original world before confirming that your backup exists.

### Q34. How do I change the difficulty?

`difficulty hard`

Replace `hard` with `easy`, `normal`, or `peaceful`.

### Q35. How do I change the time?

`time set day`

### Q36. How do I change the weather?

`weather clear`

### Q37. How do I enable command blocks?

Set this value in `server.properties`:

`enable-command-block=true`

Restart the server if necessary.

### Q38. How do I enable PvP?

Set:

`pvp=true`

in `server.properties`.

### Q39. Why are my configuration changes not working?

Some settings are read only at startup.

Stop the server safely, update the correct configuration file, and restart it.

### Q40. Why did my world reset?

Possible causes:

- The server started with a different world directory.
- The old world was not restored.
- A new installation generated a fresh world.
- The world folder was overwritten.
- The runner ended before the data was persisted.

Check the available backups and storage configuration.

---

## CONNECTION AND MULTIPLAYER

### Q41. Minecraft says Connection Timed Out.

Check that:

- The workflow is running.
- The server is running.
- Bore is connected.
- The public address is correct.
- Your internet connection is stable.

### Q42. Minecraft says Unknown Host.

Copy the complete Minecraft address from the current workflow logs.

Do not use the dashboard URL.

### Q43. Minecraft says Incompatible Version.

Your Minecraft client and server must use compatible versions.

For modded servers, check the loader and mod versions too.

### Q44. Minecraft says Failed to Verify Username.

Check your Minecraft account authentication and launcher configuration.

Do not attempt to bypass account authentication as a workaround.

### Q45. I can open the dashboard, but Minecraft cannot connect.

The dashboard and Minecraft use separate tunnels.

The dashboard can work while the Bore Minecraft tunnel is disconnected.

Inspect the Bore startup and connection logs.

### Q46. Why does my Minecraft address change?

The Bore tunnel address may be different in a new workflow session.

Use the address printed by the active workflow.

### Q47. Can Bedrock players join?

The project is designed for Java Edition.

Bedrock support requires additional compatible software and configuration.

---

## PERFORMANCE AND LAG

### Q48. My server is running, but it is lagging.

Check CPU, RAM, console messages, and TPS if available.

Large farms, entities, world generation, and mods can cause performance problems.

### Q49. My chunks load slowly.

Try reducing the client render distance.

On the server side, investigate CPU load, world generation, and storage performance.

### Q50. My FPS drops even when I am standing still.

This may be a client-side issue.

Try lowering graphics settings, render distance, particles, and entity distance.

### Q51. The dashboard shows 0% CPU. Does that mean there is no lag?

No.

A CPU percentage may be a snapshot or rounded value.

Check actual gameplay, server tick performance, and console warnings.

### Q52. The dashboard shows TPS N/A.

The dashboard may not have received TPS data.

Check whether the selected server software exposes the expected metric.

### Q53. Why does the server say Can't keep up!?

Minecraft is taking too long to process ticks.

Reduce the server workload and investigate CPU-intensive mods, entities, and world generation.

### Q54. Will allocating more RAM fix everything?

No.

More RAM cannot fix every CPU, network, storage, or client performance problem.

---

## MODS AND PLUGINS

### Q55. Why is my mod not loading?

Check the mod's Minecraft version, loader, dependencies, and installation directory.

### Q56. Why does the server crash after adding a plugin?

The plugin may be incompatible with your server software or Minecraft version.

Remove the suspected plugin and inspect the startup logs.

### Q57. Can I use Forge mods on Fabric?

No, not normally.

Forge and Fabric are different modding ecosystems. Use mods designed for the selected loader.

### Q58. Can I use Paper plugins on Vanilla?

Vanilla does not provide Bukkit/Paper plugin support.

Use compatible server software.

### Q59. Why can my friend not join my modded server?

Check that both clients use compatible Minecraft, loader, and mod versions.

### Q60. Can I update my mods without stopping the server?

Do not replace mod files while the server is actively using them.

Stop the server, update the files, and restart it.

---

## DASHBOARD METRICS AND SERVER STATUS

### Q61. The dashboard says RUNNING, but I cannot join.

RUNNING may only indicate that the process is active.

Check the Minecraft console for the successful startup message and verify the Bore tunnel separately.

### Q62. The dashboard says STOPPED, but Minecraft is still running.

The dashboard may have stale status information or may not be monitoring the correct process.

Refresh the dashboard and inspect the workflow logs.

### Q63. The RAM value keeps changing. Is that normal?

Yes.

Java memory usage changes during world loading, garbage collection, player activity, and mod operations.

### Q64. The uptime counter reset. Why?

The dashboard may have detected a new process or a new hosting session.

### Q65. The console is not updating.

Check whether the server is running and whether the dashboard is receiving console output.

If the server is unresponsive, inspect the workflow logs.

---

## WORKFLOW AND SESSION QUESTIONS

### Q66. What happens when the session expires?

The workflow ends and the temporary runner is released.

The server and tunnels stop.

### Q67. Can I restart the workflow?

Yes, by starting another run.

However, the previous world and configuration must have been saved and restored through a persistence system if you want to continue the same world.

### Q68. Will my server automatically remain online forever?

No. GitHub Actions runners are temporary and have execution limits.

### Q69. Can I use this project for a large public SMP?

The project can serve as a starting point for experimentation and temporary hosting.

A large public SMP requires reliable persistent storage, appropriate infrastructure, backups, monitoring, and a hosting arrangement suitable for continuous operation.

### Q70. Can I run multiple servers?

The architecture can be extended to multiple instances, but each requires independent storage, resource allocation, networking, and management.

Follow GitHub's applicable Actions limits and acceptable-use policies.

---

# 15. SECURITY AND IMPORTANT INFORMATION

- Never share your dashboard owner password.
- Never publish private access tokens.
- Do not expose RCON publicly.
- Back up your Minecraft world before major changes.
- Use compatible mods and plugins.
- Stop the server safely before modifying important files.
- Keep your workflow and dashboard updated.
- Do not assume temporary runner files are persistent.
- Do not expose administrative access to people you do not trust.

If administrative support access is provided by the hosting platform, it should follow the platform's published rules and authorization process.

---

# 16. NEED HELP?

If your problem is not covered in this guide, provide the following information when requesting support:

1. Minecraft version.
2. Server software.
3. Java version.
4. Selected RAM allocation.
5. What you were doing when the issue happened.
6. The relevant console error.
7. The relevant workflow log section.

Never share passwords, private tokens, or other credentials.

---

# THANK YOU!

Thank you for using Minecraft Hosting!

Whether you are creating a small Survival world with friends, building a modded Forge server, experimenting with Paper plugins, or learning how Minecraft server hosting works, this project is designed to give you a straightforward starting point.

Have fun, explore, build, and create amazing Minecraft experiences!

**Happy Crafting!** 


## UMN Gateway security model

Forks call the central V1.19 reusable workflow and authenticate to the temporary UMN Gateway using GitHub Actions OIDC. The Gateway accepts only tokens whose `job_workflow_ref` identifies the approved central reusable workflow. The GitHub App private key stays in the private Admin repository; no fork needs an App secret or installation. Existing Tailscale OIDC variables are still required for private instance registration and `umn.internal` DNS access. See the Admin repository's `docs/REUSABLE-WORKFLOW.md` for setup.
