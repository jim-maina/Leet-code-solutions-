class CustomStack {
    int[] stack;
    int[] inc;
    int top = -1;

    public CustomStack(int maxSize) {
        stack = new int[maxSize];
        inc = new int[maxSize];
    }

    public void push(int x) {
        if (top + 1 == stack.length) return;
        stack[++top] = x;
    }

    public int pop() {
        if (top < 0) return -1;

        int res = stack[top] + inc[top];
        if (top > 0) inc[top - 1] += inc[top];
        inc[top] = 0;
        top--;

        return res;
    }

    public void increment(int k, int val) {
        if (top < 0) return;
        int idx = Math.min(k - 1, top);
        inc[idx] += val;
    }
}
