## 回文数索引
[https://www.nowcoder.com/practice/b6edb5ca15d34b1eb42e4725a3c68eba?tpId=182&&tqId=34896&rp=1&ru=/ta/exam-all&qru=/ta/exam-all/question-ranking](https://www.nowcoder.com/practice/b6edb5ca15d34b1eb42e4725a3c68eba?tpId=182&&tqId=34896&rp=1&ru=/ta/exam-all&qru=/ta/exam-all/question-ranking)
给定一个仅由小写字母组成的字符串。现在请找出一个位置，删掉那个字母之后，字符串变成回文。请放心总会有一个合法的解。如果给定的字符串已经是一个回文串，那么输出-1。

输入：
```html
第一行包含T，测试数据的组数。后面跟有T行，每行包含一个字符串。
```

输出：
```html
如果可以删去一个字母使它变成回文串，则输出任意一个满足条件的删去字母的位置（下标从0开始）。例如：

bcc

我们可以删掉位置0的b字符。
```

```html
3
aaab
baa
aaa
```
```html
3
0
-1
```

[https://leetcode-cn.com/problems/valid-palindrome-ii/](https://leetcode-cn.com/problems/valid-palindrome-ii/)
```java
import java.util.*;

public class Main{
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.nextLine();
        for (int k = 0; k < n; k++) {
            String s = sc.nextLine();
            // 双指针
            boolean flag = true;
            int i = 0, j = s.length() - 1;
            while(i < j){
                if (s.charAt(i) != s.charAt(j)){
                    if(isVaild(s, i, j - 1)){
                        System.out.println(j);
                        flag = false;
                        break;
                    } else if(isVaild(s, i + 1, j)){
                        System.out.println(i);
                        flag = false;
                        break;
                    }
                }
                i++;
                j--;
            }
            if (flag)
                System.out.println(-1);
        }
    }
    
    public static boolean isVaild(String s, int i, int j){
        while (i < j){
            if (s.charAt(i) != s.charAt(j))
                return false;
            i++;
            j--;
        }
        return true;
    }
}
```