
class charactor:

    Number = 0
    
    def __init__(self, hp, attack, defence, mp):
        self.info = {
            'hp': hp,
            'attack': attack,
            'defence': defence,
            'mp': mp
        }
        print('player가 생성되었습니다.')
        
    def __call__(self):
        print("hp: %d, attack: %d, defence: %d " % (self.info['hp'], self.info['attack'], self.info['defence'], self.info['mp']))

    def __getitem__(self, name):
        if name in self.info.keys():
            return self.info[name]
        else:
            return "존재하지 않는 키값입니다."
    def memory(self, value):
        charactor.Number += value
        return charactor.Number
        
player_a = charactor(10, 10, 10, 40)
player_b = charactor(10, 10, 10, 40)
player_c = charactor(10, 10, 10, 40) 

player_a.memory(100)
player_b.memory(200)
print(player_c.memory(200))

# 1. 'MP' 변수 추가.
# 2. 'Charactor' 클래스의 객체 생성, 객체생성시 mp변수는 40으로 초기화,        ex) '객체이름' = '클래스 이름'(input parameter...)
# 3. charactor 클래스 객체끼리 공유할수 있는 'Number'라는 이름의  변수를 생성. 
# 4. input 파라미터로 정수를 입력받고 입력 받을때마다 입력 받은 값을 누적시켜서 더해주는 'memory'라는 이름의 매소드 생성.
# 5. 'memory' 매소드는 누적된 값을 하게 함. 
# 6. '같은 클래스 이지만 서로 다른' 3개의 객체를 이용해서 각각 1번씩만 이용해서 마지막 객체를 사용했을때 정수 500을 'ouput' 할수있게.  
