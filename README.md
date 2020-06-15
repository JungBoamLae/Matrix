#클래스 안에서 매소드 하나 만들고, 매소드 'memory' 그 매소드는 인풋
#파라미터로 값을 1개를 받아요. 그리고 그 값은 해당 매소드가 불리울 때마다
#인풋파라미터로 들어온 값이 누적되어서 더해지게 되는 클래스를 더해지게 되는 클래스를 
#아웃풋으로 누적된 값 리턴.

class charactor:
    char_cnt = 0 # 함께 참조, 변수 공유 
    uint_value = 0
    
    def __init__ (self, hp, attack, defence): #__init__으로 create 자동으로 됨
        self.info = { #변수 3개를 가진 딕셔너리
            'hp': hp,
            'attack': attack,
            'defence': defence
        }
        
        charactor.char_cnt += 1
        
        print('player가 생성되었습니다. 생성 된 유닛 수 : %d' %(charactor.char_cnt))
        
    def __call__(self):
        print("hp: %d, attack: %d, defence: %d " %(self.info['hp'], self.info['attack'], self.info['defence']))
                                                   
    def __del__(self):        
        charactor.char_cnt -= 1
        print('player가 제거되었습니다. 생성 된 유닛 수 : %d' %(charactor.char_cnt))
        
    def memory(self, value):
            charactor.uint_value = charactor.uint_value + value
            return charactor.uint_value
             
player_a = charactor(10, 20, 30)
player_b = charactor(100, 200, 300)
player_c = charactor(10, 20, 30)
#print(charactor.char_cnt)
player_d = charactor(10, 20, 30)
player_e = charactor(10, 20, 30)

player_a.memory(100)
player_b.memory(200)
print(player_c.memory(300))

print('--------------------------')
#del player_a
#del player_b
#del player_c
#del player_d
#del player_e
