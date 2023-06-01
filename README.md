# 아이펠캠퍼스 온라인4기 피어코드리뷰

- 코더 : 정우일
- 리뷰어 : 이창호

----------------------------------------------

# PRT(PeerReviewTemplate)

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?  

'''
정상적으로 동작하는 것을 확인했습니다.
유저수를 입력 받아 초기 위치를 설정하고
pipe와 snake 딕셔너리를 만들어 goto가 적용되도록 초기화하고
주사위를 굴려 goto에 해당하는지 분기문을 통과하는 루프를 짜서
프린트 문으로 현재위치를 계속 반환해
100이 넘은 플레이어가 이기도록하는 텍스트 기반 게임 완성
'''
- [O] 주석을 보고 작성자의 코드가 이해되었나요?  

'''
네.  


    while not end:
        # player 정보 출력
        print("현재 player는 ", idx, "번 유저입니다.")

        i = random.randint(1, 6)
        print("나온 주사위 값은 ", i, "입니다.")
        print("이동 전 ", idx, "번 플레이어의 위치는 ", goal[idx-1],"입니다.")

        if str(i) in pipe.keys():
            # + value만큼
            goal[idx-1] = pipe[str(i)]
        elif str(i) in snake.keys():
            # - value만큼
            goal[idx-1] = snake[str(i)]
        else:
            goal[idx-1] += i

        print("이동 후 player들의 위치는 다음과 같습니다.")
        for p in range(player):
            print(p + 1, "번 플레이어의 위치는", goal[p], "입니다.")
            if goal[p] >= 100:
                print(p + 1, "번 플레이어가 게임에서 승리하셨습니다.")
                end = True
                break
        print(' ')

        idx+=1
        if idx > player:
            idx = 1

프린트 문에 있는 주석으로 충분히 이해 가능하게 작성되었습니다
'''  

- [X] 코드가 에러를 유발할 가능성이 있나요?  
'''
없습니다.   

유저수를 무한으로 받을 수 있어서 이부분에서 제한을 걸면 더 좋지 않을까 하는 생각도 듭니다.  
'''
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?  

'''
네 제대로 이해하고 코드를 작성했습니다.
나온 주사위 값, 이동 전후 각 플레이어의 위치를 순서대로 프린트해서
최종 골이 100 이상이 될때까지 시퀀셜하게 게임 룰에 따라 게임 진행상황이 출력되도록 하여
제대로 이해해 보입니다
'''  

- [O] 코드가 간결한가요?  

'''
플레이거 만약에 3명이면
1 세트에 3개의 롤링이 있는건데
이 턴이 돌아가는 상황들이 구분될 수 있게 하면 가독성이 더 좋을 것 같다
'''
