import random
random.seed(5180043)
import sys
def sodoku():
    blockSample=[[2,1,0],
            [1,0,2],
            [0,2,1]]


    board=[[0,2,1,1,0,2,0,1,2],[1,0,2,0,2,1,1,2,0],[2,1,0,2,1,0,2,0,1],
           [2,0,1,2,1,0,2,1,0],[1,2,0,1,0,2,0,2,1],[0,1,2,0,2,1,1,0,2],
           [0,1,2,2,0,1,0,2,1],[2,0,1,0,1,2,2,1,0],[1,2,0,1,2,0,1,0,2]]
           
    
    randomNum = random.randint(0,2)
    blockRandom=[[],[],[]]
    blockRandom[0]=blockSample[randomNum]
    blockSample.remove(blockSample[randomNum])

    randomNum2 = random.randint(0,1)
    blockRandom[1]=blockSample[randomNum2]
    blockSample.remove(blockSample[randomNum2])

    blockRandom[2]=blockSample[0]
    countRow=1

    for i in range(0,9):
        count=0
        for j in range(0,9): 
            tp=board[i][j]
            if countRow<4 and count<3:
                board[i][j]=blockRandom[0][0]*3+tp+1            
            if countRow<4 and count>=3 and count<6:
                board[i][j]=blockRandom[0][1]*3+tp+1          
            if countRow<4 and count>=6:
                board[i][j]=blockRandom[0][2]*3+tp+1            
            if countRow>=4 and countRow<=6 and count<3:
                board[i][j]=blockRandom[1][0]*3+tp+1            
            if countRow>=4 and countRow<=6 and count>=3 and count<6:
                board[i][j]=blockRandom[1][1]*3+tp+1            
            if countRow>=4 and countRow<=6 and count>=6:
                board[i][j]=blockRandom[1][2]*3+tp+1            
            if countRow>6 and count<3:
                board[i][j]=blockRandom[2][0]*3+tp+1            
            if countRow>6 and count>=3 and count<6:
                board[i][j]=blockRandom[2][1]*3+tp+1          
            if countRow>6 and count>=6:
                board[i][j]=blockRandom[2][2]*3+tp+1            
            count = count + 1
            if count == 9:
                countRow = countRow + 1

    board[1],board[3]=board[3],board[1]
    board[2],board[6]=board[6],board[2]
    board[7],board[5]=board[5],board[7]
    return board
sodoku = sodoku()


fatherBo=[]
for k in range(1,4):
        fatherRow=[]
        fatherRow=list(range((k-1)*3,k*3))
        for j in range(1,4):
            fatherColl=[]
            fatherColl=list(range((j-1)*3,j*3))
            fatherBo.append([fatherRow,fatherColl])

 
def hole(sodoku,blockRandom):
    for i in blockRandom:
        sodoku[i[0]][i[1]]=0
numberHole=int(int(sys.argv[1])/9)
puzzle=sodoku.copy()
for i in fatherBo:
    blockRandom=[]
    for k in i[0]:
        for c in i[1]:
            blockRandom.append([k,c])
    blockRandom=random.sample(blockRandom,numberHole)
    hole(sodoku,blockRandom)




filename = sys.argv[2]
f = open(filename,'w')
for i in puzzle:
    line = str(i).replace("[","")
    line = line.replace("]","")
    f.write(line)
    f.write('\n')
f.close()

f = open(filename)
print("The content of output.txt file is as follows:\n")
print(f.read())
f.close()

