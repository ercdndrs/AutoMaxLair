# Changelog
## v0.2-beta
*	Initial stable public release.
*	Greatly improved Pokemon and move selection from development versions.
## v0.3
*	Implemented optional ball selection for both rental Pokemon and boss Pokemon.
*	Fixed a bug where Wide Guard users would Dynamax and use Max Guard instead.
	*	Wide Guard is now weighted fairly well.
*	Refactoring.
## v0.4
*	Added alternate modes that reset the game to preserve rare balls and/or good seeds.
	*	This mode was added with help of user fawress on the Pokemon Automation Discord.
	*	The “ball saver” mode force quits and restarts the game if the legendary is caught but is not shiny.
	*	The “strong boss” mode force quits and restarts the game if the legendary is caught and none of the Pokemon are shiny
	*	Both modes can “lock on” to a good path, since the path is conserved if the game is reset before the end of the run.
	*	Be mindful that repeated resets will incur a Dynite Ore cost, in contrast to the regular mode that accumulates Dynite Ore.
	*	The “strong boss” mode is recommended for difficult bosses where even a good seed can sometimes lose.
	*	This mode will increase the win rate against any boss, but repeated wins will quickly deplete all your Dynite Ore.
*	Fixed move scoring issues, including incorrect calculations that undervalued Max Steelspike derived from Steel Roller and overvalued Triple Axel.
*	Fixed an issue where Max Moves were overvalued by a factor of 100.
*	Added a counter for shiny Pokemon caught.
*	Adjusted detection rectangles to properly detect text when the Switch screen size is 100% (rectangles were previously optimized for a non-standard size of 96%).
*	Mitigated an issue where the bot would occasionally get stuck after dropping a button press in the battle routine.
*	Fixed an issue that caused Pokemon caught along the run to be scored incorrectly when determining whether to swap rental Pokemon or not.
## v0.5
*	Redesigned the way that the different sequences are processed to make the program run more smoothly and consistently.
	*	The visual display and button presses are now handled by different threads, which reduces FPS drops when text is being read and allows the button sequences to be handled in a linear fashion (instead of relying on a timer and substages to dictate the next step).
*	Updated the “ball saver” and “strong boss” modes to gracefully handle running out of Dynite Ore.
*	“Ball saver” mode quits when there is insufficient ore to continue resetting.
*	“Strong boss” mode finishes the run without resetting if there is insufficient ore for another reset.
*	Miscellaneous bug fixes and improvements
## v0.6
* Added support for multiple languages within the Pokemon data files.
	* All information about Pokemon is now fetched from PokeAPI.
	* Supported and verified languages include English, French, Spanish, Korean, and German.
	* Italian and Mandarin may also work but have not been tested.
* Changed how a loss (losing all 4 lives) is detected, increasing consistency.
* Detect move names, improving the accuracy of Pokemon identification.
* Updated Ball Saver mode to skip catching the boss if it can't afford to reset the game, allowing it to be run indefinitely.
* Added "Keep Path" and "Find Path" modes, which are useful against very strong bosses (e.g., Zygarde).
* Add the ability to take a pokemon from the scientist if your current pokemon is worse than average.
* Add the ability to hunt for specific stats legendary.
* Add a way to send discord message with a picture showing your latest catch.
## v0.7
* Paths through the den are now read, scored, and selected.
* Refactored code to improve readability and facilitate extension to tasks other than Dynamax Adventures in the future.
* Added support for variable hold time for button presses. The computer now sends two bytes per command, with the second byte specifying the hold time.
* Added dependencies for the microcontroller code so it can be altered and recompiled without any external tools (besides WinAVR).
* Precalculated data files are now stored in human-readable JSON format.
* Tweaked how Pokemon are scored.
* Stats checking now takes nature into account.
* Changed how certain events are detected, improving efficiency and reducing reliance on Tesseract.
* Improved path selection.
* Improved config file.
* Improved stats checking.
* More improvements on the way!
## v0.8
* Weather and terrain are now taken into consideration.
* The teammates are now detected.
* Improve the config file validation by asserting at the startup.
* Add a UI to be able to easily edit the config file.
* Detect ball type using sprites instead of text
* Automatically detect ball numbers instead of relying on users to input them in the config file
* Add compatibility for the PABotBase hex file in addition to the custom RemoteControl hex
* Detect weather and terrain
## v1.0
* Link PABotBase hex files
* Use the PABotBase hex by default
