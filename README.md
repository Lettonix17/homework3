# homework3
public class DynamicArray {
    private int[] array;
    private int size;
    public DynamicArray(int initialCapacity) {
        array = new int[initialCapacity];
        size = 0;
    }
    public void add(int value) {
        int[] newArray = new int[size + 1];
        for (int i = 0; i < size; i++) {
            newArray[i] = array[i];
        }
        newArray[size] = value;
        size++;
        array = newArray;
    }
    public int get(int index) {
        if (index < 0 || index >= size) {
            throw new IndexOutOfBoundsException("Index out of bounds");
        }
        return array[index];
    }
    public void remove(int index) {
        if (index < 0 || index >= size) {
            throw new IndexOutOfBoundsException("Index out of bounds");
        }
        int[] newArray = new int[size - 1];
        for (int i = 0, j = 0; i < size; i++) {
            if (i != index) {
                newArray[j++] = array[i];
            }
        }
        size--;
        array = newArray;
    }
    public int size() {
        return size;
    }
}
