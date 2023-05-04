# CSCI_1111_OOP_Coursework
 This repository contains my coursework for CSCI 1111 - Object Oriented Programming I at Southwest Tech.

# Connect 4 Game

## Synopsis
 This code will create a digital version of the board game connect 4. The key differences being that the player count go's up to 6 with each player being able to select a color to player as. The board size can be run at default with a width of 7 and a height of 6, or be customized by the player. Each player will then select a column/row to drop a piece down and when enough pieces of the same color have lined up the game will be won.


## Motivation
I felt like it would take everything that I've learned recently and put it all into one program.

## How to Run
The only files that are needed to run this program are all included in the project folder and can just be imported into a code editor.

## Code Example
This is one of 4 loops that run to check if a piece has lined up for a player to win the game.
```
		for (int height = 0; height < boardHeight && winCondition != userSelectedWinCondition; height++) {
			for (int width = 0; width < boardWidth && winCondition != userSelectedWinCondition; width++) {
				if (gameBoard[height][width].boardSpace != " ") {
					winCondition = 0;
					winCondition++;
					for (int h1 = 0; h1 < userSelectedWinCondition && winCondition != userSelectedWinCondition; h1++) {
						if (h1 + height + 1 < boardHeight) {
							if (gameBoard[h1 + height][width].boardSpace == gameBoard[h1 + height + 1][width].boardSpace) {
								winCondition++;
							}
							
							else {
								winCondition = 0;
								break;
							}
							
						}
						
					}

                }

            }

## Tests
Here are a few examples of the JUnit test that I was running to make sure my methods worked.

	int boardHeight = 6;
	int boardWidth = 7;
	int playerCount = 2;
	int piecesInARow = 4;
	int winCondition = 0;
	String useDefault = "yes";
	Player[] testPlayer = new Player[2];
	BoardSpace[][] testBoard = new BoardSpace[boardHeight][boardWidth];
	
	@Test
	public void testGetMode() {
		assertEquals(Game.getMode(), useDefault);
	}

	@Test
	public void testGetWinCondition() {
		assertEquals(Game.getWinCondition(boardHeight, boardWidth), piecesInARow);
	}
	
	@Test
	public void testGetPlayerCount() {
		assertEquals(Game.getPlayerCount(), playerCount);
	}
	
	@Test
	public void testPlayerOrder() {
		assertEquals(Game.playerOrder(playerCount), testPlayer[playerCount]);
	}
