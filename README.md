# SoringBowlingGame2
The game consists of 10 frames as shown above.  In each frame the player has
two opportunities to knock down 10 pins.  The score for the frame is the total
number of pins knocked down, plus bonuses for strikes and spares.

A spare is when the player knocks down all 10 pins in two tries.  The bonus for
that frame is the number of pins knocked down by the next roll.  So in frame 3
above, the score is 10 (the total number knocked down) plus a bonus of 5 (the
number of pins knocked down on the next roll.)

A strike is when the player knocks down all 10 pins on his first try.  The bonus
for that frame is the value of the next two balls rolled.

In the tenth frame a player who rolls a spare or strike is allowed to roll the extra
balls to complete the frame.  However no more than three balls can be rolled in
tenth frame.



public class Game {
	int roll[] = new int[21];
	
	public void roll() {
		int pins[] = null;
		roll = pins;
	}
	public int main(){
		int score = 0;
		int scoreFrame = 0;
		for (int frame = 0; frame < 10; frame++) {
		      if (strike(scoreFrame)) {
		        score += 10 + strikeBonus(scoreFrame);
		        scoreFrame++;
		      } else if (spare(scoreFrame)) {
		        score += 10 + spareBonus(scoreFrame);
		        scoreFrame += 2;
		      } 
		}
		return score;
	}
	public boolean strike(int scoreFrame) {
		return  roll[scoreFrame] ==  10;
	}
	
	public int strikeBonus(int scoreFrame) {
		return roll[scoreFrame+1] + roll[scoreFrame+2];
	}
	
	public boolean spare(int scoreFrame) {
		return roll[scoreFrame] + roll[scoreFrame+1] == 10;
	}
	
	public int spareBonus( int scoreFrame){
		return roll[scoreFrame+2];
	}	
}
