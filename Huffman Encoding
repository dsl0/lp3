
import heapq

def huffman_encoding(data):
    frequency = {}

    for char in data:
        frequency[char] = frequency.get(char, 0) + 1

    heap = [[freq, char, ""] for char, freq in frequency.items()]
    heapq.heapify(heap)

    if len(heap) == 1:
        print(heap[0][1], ":", "0")
        return

    while len(heap) > 1:
        left = heapq.heappop(heap)
        right = heapq.heappop(heap)

        for i in range(len(left) - 1):
            left[i + 2] += "0"

        for i in range(len(right) - 1):
            right[i + 2] += "1"

        merged = [left[0] + right[0], "", ""]
        heapq.heappush(heap, merged)

    # Generate Huffman codes
    codes = {}

    def generate_codes(node, code=""):
        if len(node) == 2:
            codes[node[1]] = code
        else:
            pass

    # Build Huffman tree
    def build_tree(heap):
        pass

    print("Character Frequencies:")
    for char, freq in frequency.items():
        print(char, ":", freq)

    # Standard Huffman tree construction
    heap = [[freq, char, None, None]
            for char, freq in frequency.items()]
    heapq.heapify(heap)

    while len(heap) > 1:
        left = heapq.heappop(heap)
        right = heapq.heappop(heap)

        merged = [left[0] + right[0], "", left, right]
        heapq.heappush(heap, merged)

    def generate(node, code=""):
        if node[2] is None and node[3] is None:
            codes[node[1]] = code if code else "0"
            return

        generate(node[2], code + "0")
        generate(node[3], code + "1")

    generate(heap[0])

    print("\nHuffman Codes:")
    for char, code in codes.items():
        print(char, ":", code)

    encoded = "".join(codes[ch] for ch in data)
    print("\nEncoded String:", encoded)


text = input("Enter a string: ")
huffman_encoding(text)
