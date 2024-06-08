import java.util.*;

class Main {
  static String[][] grid = new String[25][55];

  public static void print(String[][] grid) {
    String[] empty = new String[55];
    for (int i = 0; i < empty.length; i++) {
      empty[i] = "  ";
    }
    for (int i = 0; i < grid.length; i++) {
      if (!grid[i].equals(empty)) {
        for (int x = 0; x < grid[i].length; x++) {
          System.out.print(grid[i][x]);
        }
      }
      System.out.println();
    }
  }

  private static int count(int idx1, int idx2) {
    int count = 0;
    if (idx1 != 0) {
      if (idx2 != 0) {
        if (grid[idx1 - 1][idx2 - 1] == "[]") {
          count++;
        }
      }
      if (grid[idx1 - 1][idx2] == "[]") {
        count++;
      }
      if (idx2 != grid[idx1].length - 1) {
        if (grid[idx1 - 1][idx2 + 1] == "[]") {
          count++;
        }
      }
    }
    if (idx2 != 0) {
      if (grid[idx1][idx2 - 1] == "[]") {
        count++;
      }
    }
    if (idx2 != grid[idx1].length - 1) {
      if (grid[idx1][idx2 + 1] == "[]") {
        count++;
      }
    }
    if (idx1 != grid.length - 1) {
      if (idx2 != 0) {
        if (grid[idx1 + 1][idx2 - 1] == "[]") {
          count++;
        }
      }
      if (grid[idx1 + 1][idx2] == "[]") {
        count++;
      }
      if (idx2 != grid[idx1].length - 1) {
        if (grid[idx1 + 1][idx2 + 1] == "[]") {
          count++;
        }
      }
    }
    return count;
  }

  public static void play() {
    ArrayList<Integer[]> removeIdxs = new ArrayList<Integer[]>();
    ArrayList<Integer[]> addIdxs = new ArrayList<Integer[]>();

    for (int i = 0; i < grid.length; i++) {
      for (int x = 0; x < grid[i].length; x++) {
        if (grid[i][x] == "[]") {
          if (count(i, x) < 2 || count(i, x) > 3) {
            removeIdxs.add(new Integer[] {i, x});
          }
        }
        if (grid[i][x] == "  ") {
          if (count(i, x) == 3) {
            addIdxs.add(new Integer[] {i, x});
          }
        } 
      }
    }
    for (int i = 0; i < removeIdxs.size(); i++) {
      grid[removeIdxs.get(i)[0]][removeIdxs.get(i)[1]] = "  ";
    }
    for (int i = 0; i < addIdxs.size(); i++) {
      grid[addIdxs.get(i)[0]][addIdxs.get(i)[1]] = "[]";
    }
  }
  
  public static void main(String[] args) {
    int concentration = 8;
    String t = new String();
    Scanner scanner1 = new Scanner(System.in);
    t = scanner1.nextLine();
    for (int i = 0; i < grid.length; i++) {
      for (int x = 0; x < grid[i].length; x++) {
        if ((int) (Math.random() * 10) < concentration && (t.equals("random") || t.equals("r"))) {
          grid[i][x] = "[]";
        } else {
          grid[i][x] = "  ";
        }
      }
    }
    if (t.equals("custom") || t.equals("c")) {
      grid[1][2] = "[]";
      grid[2][3] = "[]";
      grid[3][1] = "[]";
      grid[3][2] = "[]";
      grid[3][3] = "[]";
   }

    while (true) {
      print(grid);
      System.out.println("──────────────────────────────────────────────────────────────────────────────────────────────────────────────");
      t = scanner1.nextLine();
      System.out.print("\033[H\033[2J"); 
      play();
    }
  }
}
