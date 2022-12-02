### Task 8kyu:

Localize The Barycenter of a Triangle

[Task link](https://www.codewars.com/kata/5601c5f6ba804403c7000004/train/java)

#### Solution:
```
class Barycenter {
    
    public static double[] barTriang(double[] x, double[] y, double[] z)
    {
        double [] arr = new double[2];
        arr[0] = (double)((int)Math.round((x[0] + y[0] + z[0])/3*10000))/10000;
        arr[1] = (double)((int)Math.round((x[1] + y[1] + z[1])/3*10000))/10000;
        return arr;
    }
}
```

#### Fav solution:
```
import java.text.DecimalFormat;
class Barycenter {
    
    public static double[] barTriang(double[] x, double[] y, double[] z)
    {
         DecimalFormat decimalFormat = new DecimalFormat("#.####");
        double x1 = x[0];
        double y1 = x[1];

        double x2 = y[0];
        double y2 = y[1];

        double x3 = z[0];
        double y3 = z[1];

        double resultX;
        double resultY;
        double[] result = new double[2];

        double xy = Math.sqrt(((x2 - x1) * (x2 - x1)) + ((y2 - y1) * (y2 - y1)));
        double yz = Math.sqrt(((x3 - x2) * (x3 - x2)) + ((y3 - y2) * (y3 - y2)));
        double yx = Math.sqrt(((x1 - x3) * (x1 - x3)) + ((y1 - y3) * (y1 - y3)));
        double sum = xy + yz;

        if (sum > yx) {
            resultX = (x1 + x2 + x3) / 3;
            resultY = (y1 + y2 + y3) / 3;
            result[0] = Double.parseDouble(decimalFormat.format(resultX));
            result[1] = Double.parseDouble(decimalFormat.format(resultY));
        }
        return result;
    }
}
```

#### Comment:
Although this solution seems big, it looks more correct.


### Task 8kyu:

Given an unsorted array of 3 positive integers [ n1, n2, n3 ], determine if it is possible to form a Pythagorean Triple using those 3 integers.
A Pythagorean Triple consists of arranging 3 integers, such that:
a2 + b2 = c2

[Task link](https://www.codewars.com/kata/5951d30ce99cf2467e000013/train/java)

#### Solution:
```
import java.util.Arrays;

public class PythagoreanTriple {
	public int pythagoreanTriple(int[] a) {
    return a[0] * a[0] + a[1] * a[1] == a[2] * a[2] ? 1 : 0;
	}
}
```

#### Fav solution:
```
import java.util.Arrays;
public class PythagoreanTriple {
		public int pythagoreanTriple(int[] triple){
		    return Math.pow(triple[2],2)==Math.pow(triple[0],2)+Math.pow(triple[1],2)?1:0;
	}
}
```

#### Comment:
Finally got around to using this build. The favorite solution differs in design, but not in the essence of the solution.
