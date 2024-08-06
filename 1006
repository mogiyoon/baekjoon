# 첫째 줄에 테스트 케이스의 개수 T가 주어진다. 각 테스트 케이스는 다음과 같이 구성되어있다.
# 첫째 줄에는 (구역의 개수)/2 값 N과 특수 소대원의 수 W가 주어진다. (1 ≤ N ≤ 10000, 1 ≤ W ≤ 10000).
# 둘째 줄에는 1~N번째 구역에 배치된 적의 수가 주어지고, 
# 셋째 줄에는 N+1 ~ 2N번째 구역에 배치된 적의 수가 공백으로 구분되어 주어진다. (1 ≤ 각 구역에 배치된 최대 적의 수 ≤ 10000) 
# 단, 한 구역에서 특수 소대원의 수보다 많은 적이 배치된 구역은 존재하지 않는다. (따라서, 각 구역에 배치된 최대 적의 수 ≤ W)
import copy

test_case = input()


location, warrior = input().split()
location = int(location)
warrior = int(warrior)
first_area = list(map(int, input().split()))
second_area = list(map(int, input().split()))
matrix_list = [first_area, second_area]

temp_first_area = copy.deepcopy(first_area)
temp_second_area = copy.deepcopy(second_area)
temp_matrix_list = [temp_first_area, temp_second_area]

def finder(temp_matrix, m, n, location):
    result = 3

    if (n == 0):
        if (0 < m and m < location -1):
            result += warrior_comparer(temp_matrix[n][m-1], temp_matrix[n][m])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n][m+1])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n+1][m])
            return result
        elif (m == 0):
            result += warrior_comparer(temp_matrix[n][location-1], temp_matrix[n][m])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n][m+1])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n+1][m])
            return result
        else:
            result += warrior_comparer(temp_matrix[n][m-1], temp_matrix[n][m])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n][0])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n+1][m])
            return result
    if (n == 1):
        if (0 < m and m < location -1):
            result += warrior_comparer(temp_matrix[n][m-1], temp_matrix[n][m])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n][m+1])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n-1][m])
            return result
        elif (m == 0):
            result += warrior_comparer(temp_matrix[n][location-1], temp_matrix[n][m])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n][m+1])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n-1][m])
            return result
        else:
            result += warrior_comparer(temp_matrix[n][m-1], temp_matrix[n][m])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n][0])
            result += warrior_comparer(temp_matrix[n][m], temp_matrix[n-1][m])
            return result

def warrior_comparer (value1, value2):
    if (value1 + value2 > warrior):
        return 0
    else:
        return -1

no_way_coordinate = []
one_way_coordinate = []

for m in range(location):
    for n in range(2):
        if(finder(matrix_list, m, n, location) != None):
            temp_matrix_list[n][m] = finder(matrix_list, m, n, location)
            if (temp_matrix_list[n][m] == 3):
                no_way_coordinate.append([n, m])
            elif (temp_matrix_list[n][m] == 2):
                one_way_coordinate.append([n, m])




print(temp_first_area)
print(temp_second_area)
