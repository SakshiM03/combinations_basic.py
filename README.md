# combinations_basic.py

def combinations(arr, k):
    result = []

    def backtrack(start, path):
        if len(path) == k:
            result.append(path.copy())
            return

        for i in range(start, len(arr)):
            path.append(arr[i])
            backtrack(i + 1, path)
            path.pop()

    backtrack(0, [])
    return result


numbers = [1, 2, 3, 4]

for item in combinations(numbers, 2):
    print(item)
