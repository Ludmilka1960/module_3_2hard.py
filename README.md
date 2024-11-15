def calculate_structure_sum(data_strukture):
    res = 0
    for item in data_strukture:
        if isinstance(item, list) or isinstance(item, tuple) or isinstance(item, set):
            res += calculate_structure_sum(item)
        elif isinstance(item, dict):
            res += calculate_structure_sum(item.items())
        elif isinstance(item, int or float):
            res += item
        elif isinstance(item, str):
            res += len(item)
    return res


data_structure = [
    [1, 2, 3],
    {'a': 4, 'b': 5},
    (6, {'cube': 7, 'drum': 8}),
    "Hello",
    ((), [{(2, 'Urban', ('Urban2', 35))}])
]

result = calculate_structure_sum(data_structure)
print(result)
