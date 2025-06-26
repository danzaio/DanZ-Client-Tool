# DanZ Client Tool

\<p align="center"\>
  \<img src="[https://i.imgur.com/5z5zNNz.jpeg](https://i.imgur.com/5z5zNNz.jpeg)" alt="DanZ Client Tool Logo/Screenshot" width="200"/\>
\</p\>

Hey folks,

I'm happy to be releasing the DanZ Client Tool\! It revitalizes many features from the original KBot concept. This significant update, while ensuring constant updates and a new UI, was primarily focused on **enhancing its operational discretion**. It’s free, remains in active development, and more stuff is soon to come :)

This tool is a Python-based application designed to interact with the League of Legends Client (LCU) to provide various enhancements, automation, and information retrieval features. It's a full port of the original KBot concept to Python, using Tkinter and CustomTkinter for the GUI.

The release is currently available on this GitHub repository. I'll be updating this page with more screenshots and details soon.

**Important Note: Closed Source & Obfuscation**

The distributed version of DanZ Client Tool is **closed-source and obfuscated**. This decision was made primarily to **discourage malicious actors from taking the code, adding unauthorized authentication systems, and attempting to sell it on shady Discord servers or other platforms.** This tool is intended to be free for the community and will always remain so.

While the source isn't publicly available by default, I'm committed to transparency for those with genuine interest or concerns. If you have any doubts about how a specific feature works, or if you're a developer interested in understanding parts of the codebase, please feel free to DM me – I'll happily share relevant source snippets or explanations. Furthermore, if there's strong community interest and consensus, I'm open to fully open-sourcing the project in the future.

-----

## 🌟 Features Overview

  * **Summoner Information:** Look up player profiles by Riot ID, PUUID, or Summoner ID.
  * **Profile Customization:** Change your status message, availability, profile icon, background skin, and displayed rank.
      * **New:** Customize **challenge banner, badges**, and **challenge points text**.
      * **New:** Set a **custom mastery score** display.
  * **Game & Lobby Management:**
      * Create various lobby types (Practice Tool, Draft, ARAM, Custom, etc.).
      * Set preferred roles for matchmaking.
      * Automate actions like queue accepting, champion instalocking (with backup), and auto-banning.
      * Send instant messages in champ select.
      * Multi-search your team on popular stat sites.
  * **Champion & Skin Management:**
      * View detailed information about your champions, including mastery, purchase dates, and LCU data.
      * Browse your owned skins.
      * **New:** **Sort** your owned skin list and **copy owned skin names** to your clipboard.
  * **Miscellaneous Utilities:**
      * Restart LoL UX or close the client gracefully.
      * Manage friend requests and friend groups.
      * Change your Riot ID.
      * Adjust minimap scale.
      * **New:** **Disenchant all loot of a selected type** (e.g., champion shards, skin shards).
      * **New:** Attempt to **refund the last refundable purchase** via the store API.
  * **Background Automation:** Auto-accept queues and perform champ select actions (instalock, autoban, instant message, mute, side notification) automatically.
  * **Persistent Configuration:** Saves your settings locally.
  * **New: Custom API Interaction:** Send custom HTTP/HTTPS requests to the LCU, Riot Client, or external URLs, and invoke legacy LCDS methods.
  * **New: Settings:** Configure tool-specific settings like auto-renaming the executable and the League of Legends installation path.

-----

## 🖼️ Screenshots

*I'll be updating this section with new screenshots soon\!*

-----

## ⚙️ Prerequisites

  * Windows Operating System (due to `psutil` for process searching and `win32api` for file version, though `win32api` can be made optional).
  * League of Legends client installed and running.

-----

## 🚀 Installation & Usage

1.  **Download:**
      * Go to the [Releases Page](https://github.com/danzaio/DanZ-Client-Tool/releases/tag/v0.2) of this repository.
      * Download the latest version.
2.  **Run:**
      * Ensure your League of Legends client is running and you're logged in.
      * Run the downloaded executable.
3.  **Connect:**
      * The tool will automatically try to connect to your League client. The connection status shows up in the bottom status bar.
      * If you're not connected, try the "Reconnect" button.

-----

## 📖 Detailed Functionality

The tool has several tabs, each with different features:

### 🏠 Info Tab

  * **Summoner Lookup:**
      * **Input Field:** Enter a `Name#Tag`, PUUID, or Summoner ID.
      * **By Riot ID Button:** Fetches summoner data using the entered `Name#Tag`.
      * **By PUUID Button:** Fetches summoner data using the entered PUUID.
      * **By Summoner ID Button:** Fetches summoner data using the entered Summoner ID.
      * **My Info Button:** Fetches data for your currently logged-in account.
  * **Results Textbox:** Shows the JSON response from the LCU for the lookup.
  * **Actions (uses displayed Summoner ID/Riot ID from the last successful lookup):**
      * **Invite to Lobby Button:** Invites the looked-up summoner to your current lobby.
      * **Add Friend Button:** Sends a friend request to the looked-up summoner (uses their Riot ID).

-----

### 👤 Profile Tab

  * **Status Message:**
      * **Entry Field:** Set your custom status message (availability text).
      * **Set Status Button:** Applies the message.
  * **Availability:**
      * **Segmented Button (online, away, mobile, offline):** Sets your chat availability.
  * **Icon ID:**
      * **Entry Field:** Input a numerical Profile Icon ID.
      * **Set Icon Button:** Changes your profile icon.
  * **Background:**
      * **Champion ComboBox:** Select a champion for your profile background.
      * **Skin ComboBox:** Select a skin for the chosen champion (this updates based on your champion selection).
      * **Champion Icon & Skin Splash Preview:** Shows a preview of the selected champion's icon and the skin's splash art.
      * **Set Background Button:** Applies the selected champion skin as your profile background.
  * **Chat Connection:**
      * **Disconnect Chat Button:** Disconnects your client from Riot's chat servers (you'll appear offline to others, but you can still see messages).
      * **Reconnect Chat Button:** Re-establishes connection to chat servers.
  * **Rank Display:**
      * **Queue ComboBox:** Select the queue type for your displayed rank (e.g., Solo/Duo, Flex).
      * **Tier ComboBox:** Select the rank tier (e.g., GOLD, PLATINUM).
      * **Division ComboBox:** Select the rank division (e.g., I, IV).
      * **Set Rank Button:** Applies the selected rank to your profile display.
      * **Empty Rank Button:** Clears your displayed rank.
  * **New: Challenge Banner & Badges:**
      * **Invisible Banner Button:** Sets your profile banner to an invisible state.
      * **Challenge Badges ComboBox:** Select a mode for your challenge badges (`Empty`, `Copy 1st`, `Glitched 0-5`).
      * **Set Badges Button:** Applies the selected badge configuration.
  * **New: Challenge Points Text:**
      * **Entry Field:** Set custom text for your challenge points display.
      * **Set Points Text Button:** Applies the custom text.
      * **Set Crystal Level Button:** Uses the selected rank tier from the "Rank Display" section to set your challenge crystal level.
  * **New: Mastery Score:**
      * **Entry Field:** Input a custom mastery score.
      * **Set Mastery Score Button:** Applies the custom mastery score.

-----

### 🎮 Game Tab

  * **Create Lobby:** Buttons to quickly create lobbies for:
      * Practice Tool
      * Draft Pick
      * Solo/Duo
      * Flex SR
      * ARAM
      * Quickplay
      * Custom Blind SR (5v5 Summoner's Rift)
  * **Roles:**
      * **Primary Role ComboBox:** Select your preferred primary role.
      * **Secondary Role ComboBox:** Select your preferred secondary role.
      * **Set Roles Button:** Applies these roles for matchmaking.
  * **Automatic Actions:**
      * **Auto Accept Queue Switch:** Automatically accepts the queue when it pops.
      * **Instalock Switch:** Enables instalocking.
          * **Champion ComboBox:** Select the champion to instalock (lists owned/F2P champs).
          * **Delay Entry (ms):** Set a delay before locking in.
          * **Backup Champion ComboBox:** Select a backup champion if your primary instalock choice is banned or picked.
          * **Dodge if Instalock Banned Switch:** If your primary instalock champ is banned or picked by the enemy, the tool will automatically dodge the queue (only works if Instalock is enabled).
      * **Autoban Switch:** Enables auto-banning.
          * **Champion ComboBox:** Select the champion to auto-ban (lists all champs).
          * **Delay Entry (ms):** Set a delay before banning.
      * **Instant Mute Team Switch:** Automatically mutes all teammates in champ select.
      * **Side Notification Switch:** Sends a message in champ select chat indicating which side (Blue/Red) your team is on.
  * **Instant Message (Champ Select):**
      * **Message Entry:** The text to be sent in champ select.
      * **Delay Slider (ms):** The initial delay before sending the first message.
      * **Times Entry:** How many times to send the message.
      * **Delay Between Slider (ms):** The delay between sending multiple messages.
      * **Send Message Now Button:** Manually sends the configured message to the current champ select chat.
  * **Misc Game Actions:**
      * **Start Queue Button:** Starts the matchmaking queue for the current lobby.
      * **Dodge (Champ Select) Button:** Attempts to dodge the current champ select.
      * **Multi-Search Provider ComboBox:** Select your preferred stats website (OP.GG, U.GG, etc.).
      * **Multi-Search Team Button:** Opens the selected website with your current team's summoner names pre-filled.
  * **Ultimate Spellbook Force Summs:**
      * **Jungle Button:** Forces Smite + Flash/Ghost (Flash if available) for Ultimate Spellbook.
      * **Lane Button:** Forces Exhaust/Ignite + Flash/Ghost for Ultimate Spellbook.

-----

### 🏆 Champions Tab

  * **Sort by:** Radio buttons to sort the champion list by Name, Acquired Date, Mastery Points, ID, or Last Played.
  * **Filters:**
      * **Search Entry:** Filter champions by name or alias.
      * **Role ComboBox:** Filter by DDragon-defined champion roles (e.g., Fighter, Mage).
      * **Owned CheckBox:** Show only owned champions.
      * **F2P CheckBox:** Show only Free-to-Play champions.
      * **Chest CheckBox:** Show only champions for whom a Hextech chest is available.
  * **Load/Refresh Button:** Loads or reloads your champion data from the LCU.
  * **Champions Count Label:** Shows `Displayed / Total` champions.
  * **Champion Table:** Displays a sortable list of champions with columns for ID, Name, Alias, LCU Roles, Mastery Level, Mastery Points, Last Played, Acquired Date, Status, and Chest availability.
      * Selecting a champion in this table populates the "Champion Details" panel.
  * **Champion Details Panel (Scrollable):**
      * **Basic Info:** Name, Title.
      * **Icon & LCU Summary:** Champion Square Portrait (from LCU), Alias, LCU Roles, Status (Owned, F2P, Rental), Rental Info.
      * **DDragon Roles:** Roles as defined by Data Dragon.
      * **Mastery Summary:** Level, Points, Chest, Tokens.
      * **Full Mastery Details:** Points Since Last Level, Points Until Next Level, Highest Grade, Last Played, Formatted Points, Formatted Goal.
      * **LCU Champion Data:** Active, Bot Enabled, F2P Reward, Ranked Enabled, Acquired Timestamp.
      * **Tabs:**
          * **Abilities:** Shows champion passive and abilities (Q, W, E, R) with icons, names, and descriptions from Data Dragon.
          * **Skins (Owned):** Shows splash art, name, and purchase date for skins you own for the selected champion (requires skins to be loaded from the "Skins" tab first).

-----

### 🎨 Skins Tab

  * **Load/Refresh Owned Skins Button:** Loads your owned skin inventory from the LCU.
  * **New: Sort by:** Radio buttons to sort the skin list by Name, Champion, ID, or Purchase Date.
  * **New: Copy Names:**
      * **Separator Entry:** Define a separator character for copying names (e.g., `,` for comma-separated, `\n` for newlines).
      * **Copy Names Button:** Copies all owned skin names to your clipboard using the specified separator.
  * **Skins Count Label:** Shows the total number of skins owned.
  * **Skins Table:** Displays a sortable list of your owned skins with columns for Skin Name, Champion, Skin ID, and Purchase Date & Time.

-----

### ⚙️ Misc Tab

  * **Process Control:**
      * **Restart UX Button:** Sends a command to kill and restart the League Client's UX process (useful if it's bugged).
      * **Close Client (Properly) Button:** Sends a command to gracefully shut down the League Client.
  * **Friend Requests:**
      * **Accept All Friend Requests Button:** Accepts all pending friend requests.
  * **Remove Friends from Group:**
      * **Friend Group ComboBox:** Select a friend group (including "Default (All Friends)"). This populates after LCU connection.
      * **Remove Friends From: Button:** **PERMANENTLY removes all friends belonging to the selected group. Use with extreme caution\!**
  * **Change Riot ID:**
      * **Game Name Entry:** Your desired new game name.
      * **\#Tag Entry:** Your desired new tag line (without the '\#').
      * **Change Riot ID Button:** Attempts to change your Riot ID (requires confirmation).
  * **Minimap Scale:**
      * **Slider & Value Label:** Adjust the desired minimap scale (0-350).
      * **Set Scale Button:** Applies the selected minimap scale to your in-game settings.
  * **New: Disenchant All:**
      * **Disenchant All Button:** Initiates the disenchantment of all loot of the selected type.
      * **Loot Type ComboBox:** Select the specific type of loot to disenchant (e.g., `Champion Shards`, `Skin Shards`, `Eternals`).
  * **New: Refund Last Purchase:**
      * **Refund Last Purchase (Store API) Button:** Attempts to refund the most recent refundable purchase from your store history through the League of Legends store API.

-----

### 🛠️ Custom Tab (New)

This tab is for advanced users or for troubleshooting, allowing direct interaction with the League Client API (LCU) and Riot Client API, as well as legacy LCDS (League of Legends Client Data Service) calls.

  * **HTTP/HTTPS Request:**
      * **Method ComboBox:** Select the HTTP method (GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD).
      * **URL Entry:** Enter the LCU endpoint (e.g., `/lol-summoner/v1/current-summoner`) or a full external HTTPS URL.
      * **Prefill Buttons:** Quickly populate the URL and headers for common APIs like **LCU**, **Riot Client**, **Store API**, or **Ledge API**.
      * **Port Entry:** Specify a custom port (leave empty for default LCU/Riot ports).
      * **Headers Textbox:** Input custom HTTP headers (either one per line in `Key: Value` format or as a JSON object).
      * **Body Textbox:** Enter the request body (as JSON or raw text).
      * **Send Request Button:** Sends the configured HTTP request.
      * **Format JSON Response Button:** Attempts to pretty-print any JSON content in the response textbox.
      * **Response Textbox:** Displays the raw response from your request, including the status code, headers, and body.
  * **LCDS Invoke:**
      * **Destination Entry:** Enter the LCDS service destination (e.g., `statisticsService`).
      * **Method Entry:** Enter the LCDS method name (e.g., `getAggregatedStats`).
      * **Arguments Textbox:** Enter arguments as a JSON array string (e.g., `["arg1", 123, {"key":"val"}]` or `[]` for no arguments).
      * **Invoke LCDS Button:** Sends the LCDS invoke request.
      * **Response Textbox:** Displays the response from the LCDS call.

-----

### ⚙️ Settings Tab (New)

This tab provides tool-specific configuration options.

  * **Auto-rename executable on launch Switch:** (Experimental, for .py scripts only) If enabled, the tool will attempt to rename its executable file to a random name upon startup. This can potentially help with some anti-cheat detections.
  * **League Path Entry:** Displays the detected League of Legends installation directory and allows you to manually adjust it if needed.
  * **Save League Path Button:** Saves the entered League of Legends installation path to your local configuration.

-----

## 🛠️ Background Workers

The tool runs a few background threads for continuous operations:

  * **Auto Accept Worker:** Periodically checks if a queue is ready, and if "Auto Accept Queue" is enabled, it automatically accepts it.
  * **Champ Select Actions Worker:**
      * Monitors the champ select phase.
      * If **Instalock** is enabled: Picks the selected champion (or a backup, or a random one) after a configured delay. It also handles dodging if your primary instalock champion is banned or picked by the enemy and "Dodge on Ban" is enabled.
      * If **Autoban** is enabled: Bans the selected champion after a configured delay.
      * If **Instant Mute Team** is enabled: Automatically mutes all teammates once per champ select phase.
      * If **Side Notification** is enabled: Sends a chat message indicating your team's side (Blue/Red) once per champ select phase.
      * If **Instant Message** text is set: Sends the configured message(s) once per champ select phase.
  * **Riot Client Version Updater:** Periodically fetches the latest Riot Client version string, which can be useful for certain LCU authentication headers.

-----

## 🤝 Contributing

While the project is currently closed-source for the reasons mentioned above, feedback, bug reports, and feature suggestions are highly welcome\! Please reach out to me or open an issue on GitHub.
As stated, if there's significant community interest and a way to mitigate misuse, a full open-source release will be considered.

-----

## ❤️ Acknowledgements

  * **Kebs:** For the original KBot project and the invaluable LCU API documentation that made this tool possible.
  * The **League of Legends** community.

-----

## 📞 Contact

If you have questions or want to discuss the tool, you can:

  * Open an Issue on this GitHub repository.
  * DM me (DanZ) on Discord `@dan_theman369`
  * Join my Discord Server: [https://discord.gg/qqepd88jXN](https://discord.gg/qqepd88jXN)

-----
