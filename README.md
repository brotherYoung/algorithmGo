# algorithmGo
学！算！法！

#### 排序算法

* 我们先定义一个模板类，方便阅读和拓展。

      public class Example {

        public static void sort(Comparable a) {

        }

        public static boolean less(Comparable v, Comparable w) {
            return (v.compareTo(w) < 0);
        }

        public static void exch(Comparable[] a, int i, int j) {
            Comparable t = a[i];
            a[i] = a[j];
            a[j] = t;
        }

        public static boolean isSorted(Comparable[] a) {
            for(int i = 0; i < a.length; i ++) {
              if (less(a[i], a[i-1])) return false; 
            }
            return true;
        }
        public static void show(Comparable[] a) {
            for(int i = 0; i < a.length; i ++) {
              System.out.print(a[i] + " ");
            }
          }
      }

1. 简单排序

        public class Selection extends Example {

          public static void sort(Comparable[] a) {

              for(int i = 0; i < a.length; i ++) {
                  int min = i;
                  for(int j = i + 1; j < a.length; j ++) {
                    if(less(a[j], a[min])) min = j;
                  }
                  exch(a, i, min);
              }
          }

          public static void main(String[] args) {
              String[] a = {"S","O","R","T","E","X","A","M","P","L","E"};
              sort(a);
              assert(isSorted(a));
              show(a);
            }
          }



结果：A E E L M O P R S T X 

