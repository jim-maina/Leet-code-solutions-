class MyCircularQueue {
    int[] q;
    int front = 0, rear = 0, count = 0;

    public MyCircularQueue(int k) {
        q = new int[k];
    }

    public boolean enQueue(int value) {
        if (isFull()) return false;
        q[rear] = value;
        rear = (rear + 1) % q.length;
        count++;
        return true;
    }

    public boolean deQueue() {
        if (isEmpty()) return false;
        front = (front + 1) % q.length;
        count--;
        return true;
    }

    public int Front() {
        return isEmpty() ? -1 : q[front];
    }

    public int Rear() {
        return isEmpty() ? -1 : q[(rear - 1 + q.length) % q.length];
    }

    public boolean isEmpty() {
        return count == 0;
    }

    public boolean isFull() {
        return count == q.length;
    }
}
