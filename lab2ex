import java.util.*;

public class TopKFrequentNumbers {

    // Static variable to store the input array of N numbers
    private static int[] numbers;

    // Static method to identify and prioritize the top K numbers with the maximum occurrences
    public static List<Integer> findTopKFrequentNumbers(int k) {
        if (numbers == null || k <= 0 || k > numbers.length) {
            System.out.println("Invalid input parameters.");
            return null;
        }

        // Create a map to store the frequency of each number
        Map<Integer, Integer> frequencyMap = new HashMap<>();
        for (int num : numbers) {
            frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);
        }

        // Create a priority queue to store entries based on their frequencies in descending order
        PriorityQueue<Map.Entry<Integer, Integer>> priorityQueue = new PriorityQueue<>(
                (a, b) -> b.getValue().compareTo(a.getValue())
        );

        // Add entries to the priority queue
        priorityQueue.addAll(frequencyMap.entrySet());

        // Retrieve the top K numbers with the maximum occurrences
        List<Integer> topKFrequentNumbers = new ArrayList<>();
        for (int i = 0; i < k; i++) {
            topKFrequentNumbers.add(priorityQueue.poll().getKey());
        }

        return topKFrequentNumbers;
    }

    public static void main(String[] args) {
        // Sample Input Array
        numbers = new int[]{7, 10, 11, 5, 2, 5, 5, 7, 11, 8, 9};

        // Specify the value of K
        int k =4;

        // Find the top K numbers with the maximum occurrences
        List<Integer> result = findTopKFrequentNumbers(k);

        // Print the output in the specified format
        System.out.print("Given an array {");
        for (int i = 0; i < numbers.length; i++) {
            System.out.print(numbers[i]);
            if (i < numbers.length - 1) {
                System.out.print(", ");
            }
        }
        System.out.println("} and K = " + k + ":");
        System.out.println("Output: " + result);
    }
}
