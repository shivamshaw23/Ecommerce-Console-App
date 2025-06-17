**E‑Commerce Store (Console Application)**

This C++ project implements a console‑based e‑commerce system that supports two types of customer orders (take‑away and home delivery), order retrieval, and a simple review system. The core data structures include an AVL tree for take‑away orders, linked list for delivery orders, graph algorithms (Dijkstra & Prim) for distance and route computations, and a Trie + KMP for efficient review storage and search.

---

## Features

1. **Product Display**
   List all available products with prices.

2. **Take‑Away Orders**

   * Place a take‑away order at the warehouse.
   * Orders stored in an **AVL tree** keyed by Order ID for balanced insertion, search, and deletion.
   * Retrieve (delete) orders when customers collect them.
   * View all pending take‑away orders in sorted order (in‑order traversal).

3. **Home Delivery Orders**

   * Compute distances between cities using **Dijkstra's algorithm** on a predefined graph of 11 cities.
   * For zones with sub‑areas, refine distance via **Prim's minimum spanning tree** on each city's local graph.
   * Calculate delivery charges (fixed rate per km) and total bill.
   * Store delivery orders in a singly linked list.
   * View all home delivery orders.

4. **Customer Reviews**

   * Add text reviews interactively.
   * Store reviews in a **Trie** for prefix‑based lookup.
   * Search within full reviews using the **KMP string search** algorithm.

## Dependencies

* C++ Standard Library
* Compiler supporting C++11 or later (e.g., g++, clang++)

## Installation & Compilation

1. Clone or download the repository:

   ```bash
   git clone https://github.com/<username>/ecommerce-console.git
   cd ecommerce-console
   ```
2. Compile the source code:

   ```bash
   g++ -std=c++11 -O2 main.cpp -o ecommerce
   ```

## Usage

Run the compiled executable in your terminal:

```bash
./ecommerce
```

Follow the on‑screen menu to:

1. Display product catalog.
2. Place take‑away orders (requires numeric Order ID).
3. Place home delivery orders (select city, sub‑area if required).
4. Retrieve a take‑away order by Order ID.
5. View all home delivery orders.
6. View all pending take‑away orders.
7. Add customer review.
8. Search customer reviews by keyword or pattern.
9. Exit the application.

## Project Structure

* `main.cpp`
  Contains the entire application: data structures, algorithms, and menu logic.

### Key Classes & Structs

* `user` / `deliveryUser` — represent customer orders and linked list nodes.
* `takeAway` — nodes for AVL tree (order ID, customer info).
* `ReviewTrie` + `TrieNode` — prefix‑tree for review storage.

### Algorithms

* **AVL Tree** (LL, RR, LR, RL rotations) — balanced BST for take‑away orders.
* **Dijkstra** — single‑source shortest paths among major cities.
* **Prim** — MST for intra‑city sub‑area distance estimation.
* **KMP** — efficient substring search within reviews.

## Customization

* **Products & Prices**: Modify `shop->product` and `shop->price` arrays.
* **City Graphs**: Edit the `graph` matrix or per‑city adjacency matrices for customized delivery zones.
* **Delivery Rate**: Change `deliveryChargesPerKM` constant in `case 3`.

## License

This project is released under the MIT License. See [LICENSE](LICENSE) for details.

---

*Happy Coding!*
