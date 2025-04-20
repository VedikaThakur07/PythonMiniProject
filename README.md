import random
import matplotlib.pyplot as plt

def estimate_pi(num_points):
    inside_circle = 0

    x_inside = []
    y_inside = []
    x_outside = []
    y_outside = []

    for _ in range(num_points):
        x = random.uniform(-1, 1)
        y = random.uniform(-1, 1)
        distance = x*2 + y*2

        if distance <= 1:
            inside_circle += 1
            x_inside.append(x)
            y_inside.append(y)
        else:
            x_outside.append(x)
            y_outside.append(y)

    pi_value = 4 * inside_circle / num_points
    print(f"Estimated π value with {num_points} points: {pi_value}")

    # Optional: Show graph
    plt.scatter(x_inside, y_inside, color='green', s=1)
    plt.scatter(x_outside, y_outside, color='red', s=1)
    plt.title(f"Monte Carlo π Estimation ({num_points} points)")
    plt.xlabel("X")
    plt.ylabel("Y")
    plt.show()

# Example run
estimate_pi(1000)
