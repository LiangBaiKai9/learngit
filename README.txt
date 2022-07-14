liang ge
class MyQueue {

    public MyQueue() {

    }
   
    private Stack<Integer> s1 = new Stack<>();
    private Stack<Integer> s2 = new Stack<>();
    public void push(int x) {
        while(!s1.isEmpty()){
            s2.push(s1.pop());
        }
        s1.push(x);
        while (!s2.isEmpty()){
            s1.push(s2.pop());
        }
    }

    public int pop() {
        return s1.pop();
    }

    public int peek() {
        return s1.peek();
    }

    public boolean empty() {
        return s1.isEmpty();
    }
}

/**
 * Your MyQueue object will be instantiated and called as such:
 * MyQueue obj = new MyQueue();
 * obj.push(x);
 * int param_2 = obj.pop();
 * int param_3 = obj.peek();
 * boolean param_4 = obj.empty();
 */





选择排序
public class Selectsort {
    public static void selectSort(int[] array) {
        for (int i = 0; i < array.length; i++) {
            int minIndex = i;
            for (int j = i + 1; j < array.length; j++) {//内层循环走完以后，minIndex一定最小元素的下标
                if (array[minIndex] > array[j]) minIndex = j;
            }
            if (array[i] == array[minIndex]) {//说明i下标这个位置的元素就是最小的
                continue;
            } else {
                int temp = array[i];
                array[i] = array[minIndex];
                array[minIndex] = temp;
            }
        }
    }
    public static void main(String[] args) {
        int[] array = new int[]{2,5,1,3,11,0,4,-1,-5,7};
        System.out.println("排序前"+ Arrays.toString(array));
        selectSort(array);
        System.out.println("排序后"+ Arrays.toString(array));
    }
}


 冒泡排序
 public class Bubblesort {
    public static void bubbleSort(int[] array){
        int len = array.length-1;
        for (int i = len; i >0 ; i--) {
            boolean flag = true;
            for (int j = 0; j < i; j++) {
                if(array[j]>array[j+1]){
                    int temp = array[j];
                    array[j] = array[j+1];
                    array[j+1] = temp;
                    flag = false;
                }
            }
            if(flag)break;
        }
    }
    public static void main(String[] args) {
        int[] array = new int[]{2,5,1,3,11,0,4,-1,-5,7};
        System.out.println("排序前"+ Arrays.toString(array));
        bubbleSort(array);
        System.out.println("排序后"+ Arrays.toString(array));
    }
}
