# Vier

Vier is four in a row for iPhone and Apple Watch: drop red discs into a seven-by-six board against yellow, and line up four across, down or diagonally first. The opponent is the device itself, and the watch app runs on its own, without the iPhone nearby. Vier has no account, no network, no ads and no analytics. It opens straight into a game, picks up where it left off, and has an Easy level built for beginners. Its desktop port, for Linux, macOS and Windows, is [vier-desktop](https://github.com/anderix/vier-desktop).

## Playing

Slide a finger sideways on the board to move the red disc over a column, then swipe down to drop it; on the watch the Digital Crown moves it too. A tap does nothing, so a stray touch can't play a move. The opponent thinks for a moment, slides its own disc over and drops it. Who moves first alternates from game to game. When someone lines up four, those discs are ringed and pulse, and the game offers Play again or Home.

Easy, Medium and Hard set how far ahead the opponent looks and how often it plays a random move instead. Every level takes a winning move when it has one; Medium and Hard also always block yours.

The Players setting on the home screen switches to two players, where two people take turns on one device with no Difficulty setting.

The iPhone and the watch each keep their own settings and their own game; nothing passes between them.

## Building

Vier is distributed as source rather than through the App Store. Open `Vier.xcodeproj` in Xcode and set your own team in `Config/Vier.xcconfig`. The `Vier` scheme builds the iPhone app with the watch app embedded. The `Vier Watch App` scheme builds the watch app alone for a watch or the simulator and runs the tests.

Nearly all the code lives in `Shared/`, which both apps compile; `#if os(watchOS)` marks what only the watch does, chiefly the Digital Crown. `Vier/` and `Vier Watch App/` hold each app's icon and the code that plays its haptics. The identity a fork changes, meaning the team id, the bundle ids and the display name, lives in `Config/Vier.xcconfig`, and the version in `Config/Version.xcconfig`. The project has no dependencies beyond Apple's frameworks.

The computer opponent is a negamax search with alpha-beta pruning in `Shared/Engine/`, which imports nothing, so it has no tie to the interface and is tested directly on board positions.

## Privacy

Vier makes no network connection. [SECURITY.md](SECURITY.md) says what it keeps on each device, and the full statement is at [excelano.com/legal/#vier](https://excelano.com/legal/#vier).

> [!WARNING]
> Do NOT submit Vier, or a copy of it under another name, to the App Store. Apple's
> App Review Guideline 4.3 treats copies of other apps as spam, and a 4.3
> finding can flag the developer account that submitted it, so that every app
> the account sends afterwards is flagged too. Build it for your own devices and keep
> it there.

## License

MIT. See [LICENSE](LICENSE).
