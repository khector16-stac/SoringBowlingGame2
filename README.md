# SoringBowlingGame2

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
