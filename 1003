# 테스트케이스 개수 T
# 건물의 개수 N, 건설순서 규칙 개수 K
# 각 건물당 걸리는 시간
# 건설 순서
# 승리하기 위해 건설해야할 건물 번호
import copy

test_case = int(input())

for i in range(test_case):
    building_num, construct_rule = input().split()
    construct_rule = int(construct_rule)
    building_time = list(input().split())
    building_time = list(map(int, building_time))
    first_building_list = []
    second_building_list = []
    first_building = 0
    second_building = 0
    route_list = []

    for i in range(construct_rule):
        first_building, second_building = input().split()
        first_building_list.append(first_building)
        second_building_list.append(second_building)

    building_for_win = input()
    route_list.append(building_for_win)
    all_route_list = []

    while (all_route_list != route_list):
        all_route_list = copy.deepcopy(route_list)
        all_route_num = len(route_list)

        for i in range(len(route_list)):
            copy_number = second_building_list.count(route_list[i][-1])

            if (route_list.count(route_list[i]) != copy_number):
                for j in range(copy_number - 1):
                    route_list.append(copy.deepcopy(route_list[i]))
                    break
            else:
                for k in range(len(route_list)):
                    for l in range(len(second_building_list)):
                        if (route_list[k][-1] == second_building_list[l] and (route_list[k] + first_building_list[l]) not in route_list):
                            route_list[k] = route_list[k] + first_building_list[l]

    time_comparer = []

    for i in range(len(route_list)):
        time_comparer.append(0)
        time_value = 0
        for j in range(len(route_list[i])):
            temp_building_num = int(route_list[i][j])
            time_value += building_time[temp_building_num-1]
            time_comparer[i] = time_value

    max_value = max(time_comparer)

    print(max_value)


#시간초과
