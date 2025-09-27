import java.util.*;

class FoodRatings {
    private Map<String, String> foodCuisine;
    private Map<String, Integer> foodRating;
    private Map<String, TreeSet<String>> cuisineFoods;

    public FoodRatings(String[] foods, String[] cuisines, int[] ratings) {
        foodCuisine = new HashMap<>();
        foodRating = new HashMap<>();
        cuisineFoods = new HashMap<>();

        for (int i = 0; i < foods.length; i++) {
            String food = foods[i];
            String cuisine = cuisines[i];
            int rating = ratings[i];

            foodCuisine.put(food, cuisine);
            foodRating.put(food, rating);

            cuisineFoods.putIfAbsent(cuisine, new TreeSet<>((a, b) -> {
                int cmp = Integer.compare(foodRating.get(b), foodRating.get(a));
                if (cmp == 0) return a.compareTo(b);
                return cmp;
            }));

            cuisineFoods.get(cuisine).add(food);
        }
    }

    public void changeRating(String food, int newRating) {
        String cuisine = foodCuisine.get(food);
        cuisineFoods.get(cuisine).remove(food);
        foodRating.put(food, newRating);
        cuisineFoods.get(cuisine).add(food);
    }

    public String highestRated(String cuisine) {
        return cuisineFoods.get(cuisine).first();
    }
}
