---
layout: post
title:  "알고리즘 - 2"
date:   2022-12-06 23:00:00 +0900
categories: jekyll update
---


import java.io.*;
import java.util.*;

public class Main {

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

        int row = 9;
        int col = 9;

        int[][] preArray = new int[row][col];
        for (int i = 0; i < row; i++) {
            StringTokenizer stTemp = new StringTokenizer(br.readLine());
            for (int j = 0; j < col; j++) {
                preArray[i][j] = Integer.parseInt(stTemp.nextToken());
            }
        }

        OptionalInt a = Arrays.stream(preArray).flatMapToInt(Arrays::stream).max();
        bw.write(a.getAsInt()+"\n");
        String graph = "";
        for (int i = 0; i < row; i++) {

            for (int j = 0; j < col; j++) {
                if(preArray[i][j] == a.getAsInt()){
                    graph = (i+1)+" "+(j+1);
                }
            }
        }

        bw.write(graph);
        bw.flush();
        bw.close();

    }
}
