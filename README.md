//자바 로또만들기 
package Lotto;
import java.util.Arrays;
public class LottoNum {
	private int[] lots;
	private int base;  //45
	private int ballNum; //6
	public LottoNum(int base, int ballNum) {
		super();
		this.ballNum = ballNum;
		this.base = base;
		//배열 생성
		lots = new int[ballNum];	
	}
	public LottoNum() {
		this(45,6);
	}
	
	public void print() {
		for (int i = 0; i < lots.length; i++) {
			if (i == lots.length-1) {
				System.out.printf("%d"+",", lots[i]);
			} else {
				System.out.printf("%d"+"," , lots[i]);
			 }
		 }
		System.out.println();
		
	}
	private int rand() {
		return (int)(Math.random() * base) +1 ;
	}
	public boolean contain(int n) {
		boolean isC = false
		for(int i = 0; i <lots.length; i++) {
			if(lots[i] == n) {
				isC = true;
				break;
			}
		}
		return isC;
	}
	
	public void make() {
		Arrays.fill(lots, 0);
		int count = 0;
		while(count != ballNum) {
			int temp = rand();
			if(! contain(temp)) {
				lots[count++] = temp;
			}
		}
		
		Arrays.sort(lots);
	}
	
	public int[] getLots() {
		return lots;
	}

}

--------------------------------------------------------------------------------

메인

package Lotto;

public class LottoNumMain {
  public static void main(String[] args) {
		LottoNum ln = new LottoNum(45,6);
		
		ln.make();
		ln.print();

	}

}

