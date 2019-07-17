```
class Card {
    private int val;
    private Suit suit;
    
    enum {
        DIAMOND,
        SPADE,
        CLUD,
        HEART
    }
    
    public Card(int val, Suit suit) {
        this.val = val;
        this.suit = suit;
    }
    
    public int getValue() {
        return val;
    }
    
    public Suit getSuit() {
        return suit;
    }
}

class BlackJack extends Card {
    
    public BlackJack(int val, Suit suit) {
        super(val, suit);
    }
    
    public boolean isAce() {
        return super.getValue() == 1;
    }
    
    public int getValue() {
        int val = super.getValue();
		if (val >= 10) {
			return 10;
		} else {
			return val;
		}
    }
    
    public Suit getSuit() {
        return super.getSuit();
    }
}

public Player {
	private int bet;
	private boolean stand;
	private boolean explode;
	private List<BlackJack> blackJackList;
	
	public Player(int bet) {
		this.bet = bet;
		this.blackJackList = new ArrayList<>();
	}
	
	public void hit(BlackJack blackJack){
		this.blackJackList.add(blackJack);
	}
	
	public int getMinPoint() {
		int point = 0;
		for (BlackJack blackJack : blackJackList) {
			point += blackJack.getValue();
		}
		return point;
	}
	
	public int getMaxPoint() {
		int point = 0;
		for (BlackJack blackJack : blackJackList) {
			point += blackJack.getValue();
		}
		return point;
	}
	
	public void setStand(boolean stand) {
		this.stand = stand;
	}
	
	public boolean isExplode() {
		if (getMinPoint() > 21) {
			return false;
		}
		return true;
	}
}
```