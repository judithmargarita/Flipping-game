# Flipping-game
Exercise Codeforces 327A
public class CodeForce02 {
    
    public static int flippingGame(int n, int[] board) {
        int result = 0;
        int i = findingI(board,n);
        int j = findingJ(board,n);
        for(int ind = i; ind <= j; ind++) {
            int element = board[ind];
            board[ind] = 1 - element; 
        }
        for(int a : board) {
            result += a;
        }
        return result;
    }
    
    private static int findingI(int[] board, int n) {
        int index = 0;
        boolean hasFound = false;
        while(!hasFound && index < n) {
            if(board[index] == 0) {
                hasFound = true;
            }else {
                index ++;
            }
        }
        return index;
    }
    
    private static int findingJ(int[] board, int n) {
        int index = n-1;
        boolean hasFound = false;
        do{
            if(board[index] == 0) {
                hasFound = true;
            } else {
                index --;
            }
        } while(!hasFound && index > 0);
        return index;
    }
}
