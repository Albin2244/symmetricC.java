

import java.util.Scanner;

public class matrix_1 {
    int row;
    int column;
    int[][] array = new int[10][10];

    public void get_matrix() {
        int rc, cc;
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter size of matrix, row count: ");
        this.row = sc.nextInt();
        System.out.print("Enter size of matrix, column count: ");
        this.column = sc.nextInt();
        System.out.print("Enter matrix elements: ");
        for (rc = 0; rc < this.row; rc++) {
            for (cc = 0; cc < this.column; cc++) {
                this.array[rc][cc] = sc.nextInt();
            }
        }
    }

    public void is_symmetric() {
        int rc, cc, flag = 0;
        int[][] transpose = new int[10][10];

        for (rc = 0; rc < this.row; rc++) {
            for (cc = 0; cc < this.column; cc++) {
                transpose[cc][rc] = array[rc][cc];
            }
        }

        for (rc = 0; rc < this.row; rc++) {
            for (cc = 0; cc < this.column; cc++) {
                if (this.array[rc][cc] != transpose[rc][cc]) {
                    flag = 1;
                }
            }
        }
        if (flag == 0) {
            System.out.println("Symmetric");
            print_symmetric_matrix(transpose);
        } else {
            System.out.println("Not Symmetric");
        }
        print_matrix(); // Print original matrix
        print_transpose_matrix(transpose); // Print transpose matrix
    }

    public void print_symmetric_matrix(int[][] matrix) {
        System.out.println("Symmetric Matrix:");
        for (int i = 0; i < this.row; i++) {
            for (int j = 0; j < this.column; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }

    public void print_matrix() {
        System.out.println("Original Matrix:");
        for (int i = 0; i < this.row; i++) {
            for (int j = 0; j < this.column; j++) {
                System.out.print(this.array[i][j] + " ");
            }
            System.out.println();
        }
    }

    public void print_transpose_matrix(int[][] matrix) {
        System.out.println("Transpose Matrix:");
        for (int i = 0; i < this.column; i++) {
            for (int j = 0; j < this.row; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        matrix_1 first = new matrix_1();
        first.get_matrix();
        first.is_symmetric();
    }
}

