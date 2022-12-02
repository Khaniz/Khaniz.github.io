import java.io.*;
import java.util.StringTokenizer;

public class Main {

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

        boolean swit = true;
        while(swit){
            StringTokenizer st = new StringTokenizer(br.readLine());
            int row = Integer.parseInt(st.nextToken());
            int col = Integer.parseInt(st.nextToken());

            if(row <= 100 && col <= 100) {
                swit = false;

                int[][] preArray = new int[row][col];
                int[][] surArray = new int[row][col];
                for (int i = 0; i < row; i++) {
                    StringTokenizer stTemp = new StringTokenizer(br.readLine());
                    for (int j = 0; j < col; j++) {
                        preArray[i][j] = Integer.parseInt(stTemp.nextToken());
                    }
                }

                for (int i = 0; i < row; i++) {
                    StringTokenizer stTemp = new StringTokenizer(br.readLine());
                    for (int j = 0; j < col; j++) {
                        surArray[i][j] = Integer.parseInt(stTemp.nextToken());
                    }
                }


                for (int i = 0; i < row; i++) {
                    for (int j = 0; j < col; j++) {
                        int resultTarget = preArray[i][j] + surArray[i][j];

                        if (j+1 == col) {
                            bw.write(resultTarget + "\n");
                        } else {
                            bw.write(resultTarget + " ");
                        }
                    }
                }
                bw.flush();
                bw.close();

                break;
            }else{
                System.out.println("------------------------------");
            }
        }



    }
}
