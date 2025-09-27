public class Main {
    public static void main(String[] args) {
        Integer[] arr = {5, 2, 9, 1, 5, 6};
        // Ascending
        Arrays.sort(arr);
        System.out.println("Ascending: " + Arrays.toString(arr));
        // Descending
        Arrays.sort(arr, Collections.reverseOrder());
        System.out.println("Descending: " + Arrays.toString(arr));
    }
}
