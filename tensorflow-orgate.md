```python
# 텐써플로우 2.0을 이용해서 OR 퍼셉트론 구현하기
```


```python
import  tensorflow  as   tf

tf.random.set_seed(777)  # 시드를 설정한다. # 일치된 값으로 생성되게 하기 위해서 777로 설정합니다.
import  numpy  as  np      
from  tensorflow.keras.models  import  Sequential   # 신경망 모델 구성
from  tensorflow.keras.layers  import  Dense  # 신경망 층 / 완전 연결계층 
from  tensorflow.keras.optimizers  import   SGD  # 경사감소법 ( 오차가 가장 작은 지점으로 경사하강 )
from  tensorflow.keras.losses   import   mse    #  오차함수 

# 데이터 준비
x = np.array( [ [0, 0], [1, 0], [0, 1], [1, 1] ] )
y = np.array( [ [0], [1], [1], [1] ] )          # OR 게이트 데이터 준비

#모델 구성하기 

model = Sequential()

#단층 퍼셉트론 신경망 만들기

model.add( Dense( 1, input_shape =( 2,  ), activation ='linear')  ) 

# 모델 준비하기

model.compile( optimizer= SGD(),         # 경사하강법 종류
                     loss= mse,                        # 오차함수 지정
                     metrics = ['acc'] )      # list 형태로 평가지표를 전달한다.  

# 학습 시키기 

model.fit(x, y, epochs = 300) 

```

    Epoch 1/300
    1/1 [==============================] - 0s 120ms/step - loss: 1.4290 - acc: 0.5000
    Epoch 2/300
    1/1 [==============================] - 0s 999us/step - loss: 1.3602 - acc: 0.5000
    Epoch 3/300
    1/1 [==============================] - 0s 1ms/step - loss: 1.2956 - acc: 0.5000
    Epoch 4/300
    1/1 [==============================] - 0s 2ms/step - loss: 1.2349 - acc: 0.5000
    Epoch 5/300
    1/1 [==============================] - 0s 2ms/step - loss: 1.1779 - acc: 0.5000
    Epoch 6/300
    1/1 [==============================] - 0s 1ms/step - loss: 1.1242 - acc: 0.5000
    Epoch 7/300
    1/1 [==============================] - 0s 2ms/step - loss: 1.0738 - acc: 0.5000
    Epoch 8/300
    1/1 [==============================] - 0s 996us/step - loss: 1.0264 - acc: 0.5000
    Epoch 9/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.9819 - acc: 0.5000
    Epoch 10/300
    1/1 [==============================] - 0s 993us/step - loss: 0.9399 - acc: 0.5000
    Epoch 11/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.9005 - acc: 0.5000
    Epoch 12/300
    1/1 [==============================] - 0s 745us/step - loss: 0.8634 - acc: 0.5000
    Epoch 13/300
    1/1 [==============================] - 0s 985us/step - loss: 0.8284 - acc: 0.5000
    Epoch 14/300
    1/1 [==============================] - 0s 712us/step - loss: 0.7955 - acc: 0.5000
    Epoch 15/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.7646 - acc: 0.5000
    Epoch 16/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.7354 - acc: 0.5000
    Epoch 17/300
    1/1 [==============================] - 0s 997us/step - loss: 0.7079 - acc: 0.5000
    Epoch 18/300
    1/1 [==============================] - 0s 997us/step - loss: 0.6820 - acc: 0.5000
    Epoch 19/300
    1/1 [==============================] - 0s 996us/step - loss: 0.6576 - acc: 0.5000
    Epoch 20/300
    1/1 [==============================] - 0s 996us/step - loss: 0.6346 - acc: 0.5000
    Epoch 21/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.6129 - acc: 0.5000
    Epoch 22/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.5925 - acc: 0.5000
    Epoch 23/300
    1/1 [==============================] - 0s 647us/step - loss: 0.5732 - acc: 0.5000
    Epoch 24/300
    1/1 [==============================] - 0s 999us/step - loss: 0.5549 - acc: 0.5000
    Epoch 25/300
    1/1 [==============================] - 0s 996us/step - loss: 0.5377 - acc: 0.5000
    Epoch 26/300
    1/1 [==============================] - 0s 987us/step - loss: 0.5215 - acc: 0.5000
    Epoch 27/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.5061 - acc: 0.5000
    Epoch 28/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.4916 - acc: 0.5000
    Epoch 29/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.4778 - acc: 0.5000
    Epoch 30/300
    1/1 [==============================] - 0s 996us/step - loss: 0.4648 - acc: 0.5000
    Epoch 31/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.4525 - acc: 0.7500
    Epoch 32/300
    1/1 [==============================] - 0s 996us/step - loss: 0.4409 - acc: 0.7500
    Epoch 33/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.4298 - acc: 0.7500
    Epoch 34/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.4193 - acc: 0.7500
    Epoch 35/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.4094 - acc: 0.7500
    Epoch 36/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.4000 - acc: 0.7500
    Epoch 37/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.3911 - acc: 0.7500
    Epoch 38/300
    1/1 [==============================] - 0s 983us/step - loss: 0.3826 - acc: 0.7500
    Epoch 39/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.3745 - acc: 0.7500
    Epoch 40/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.3668 - acc: 0.7500
    Epoch 41/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.3595 - acc: 0.7500
    Epoch 42/300
    1/1 [==============================] - 0s 997us/step - loss: 0.3525 - acc: 0.7500
    Epoch 43/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.3459 - acc: 0.7500
    Epoch 44/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.3396 - acc: 0.7500
    Epoch 45/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.3336 - acc: 0.7500
    Epoch 46/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.3278 - acc: 0.7500
    Epoch 47/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.3223 - acc: 0.7500
    Epoch 48/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.3170 - acc: 0.7500
    Epoch 49/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.3120 - acc: 0.7500
    Epoch 50/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.3072 - acc: 0.7500
    Epoch 51/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.3026 - acc: 0.7500
    Epoch 52/300
    1/1 [==============================] - 0s 998us/step - loss: 0.2982 - acc: 0.7500
    Epoch 53/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2939 - acc: 0.7500
    Epoch 54/300
    1/1 [==============================] - 0s 998us/step - loss: 0.2898 - acc: 0.7500
    Epoch 55/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2859 - acc: 0.7500
    Epoch 56/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2822 - acc: 0.7500
    Epoch 57/300
    1/1 [==============================] - 0s 996us/step - loss: 0.2785 - acc: 0.7500
    Epoch 58/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.2750 - acc: 0.7500
    Epoch 59/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2717 - acc: 0.7500
    Epoch 60/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2684 - acc: 0.7500
    Epoch 61/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2653 - acc: 0.7500
    Epoch 62/300
    1/1 [==============================] - 0s 997us/step - loss: 0.2623 - acc: 0.7500
    Epoch 63/300
    1/1 [==============================] - 0s 824us/step - loss: 0.2594 - acc: 0.7500
    Epoch 64/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.2565 - acc: 0.7500
    Epoch 65/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.2538 - acc: 0.7500
    Epoch 66/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.2511 - acc: 0.7500
    Epoch 67/300
    1/1 [==============================] - 0s 985us/step - loss: 0.2486 - acc: 0.7500
    Epoch 68/300
    1/1 [==============================] - 0s 986us/step - loss: 0.2461 - acc: 0.7500
    Epoch 69/300
    1/1 [==============================] - 0s 997us/step - loss: 0.2436 - acc: 0.7500
    Epoch 70/300
    1/1 [==============================] - 0s 946us/step - loss: 0.2413 - acc: 0.7500
    Epoch 71/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2390 - acc: 0.7500
    Epoch 72/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.2368 - acc: 0.7500
    Epoch 73/300
    1/1 [==============================] - 0s 953us/step - loss: 0.2346 - acc: 0.7500
    Epoch 74/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2325 - acc: 0.7500
    Epoch 75/300
    1/1 [==============================] - 0s 997us/step - loss: 0.2304 - acc: 0.7500
    Epoch 76/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2284 - acc: 0.7500
    Epoch 77/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.2264 - acc: 0.7500
    Epoch 78/300
    1/1 [==============================] - 0s 771us/step - loss: 0.2245 - acc: 0.7500
    Epoch 79/300
    1/1 [==============================] - 0s 950us/step - loss: 0.2226 - acc: 0.7500
    Epoch 80/300
    1/1 [==============================] - 0s 996us/step - loss: 0.2208 - acc: 0.7500
    Epoch 81/300
    1/1 [==============================] - 0s 908us/step - loss: 0.2190 - acc: 0.7500
    Epoch 82/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2173 - acc: 0.7500
    Epoch 83/300
    1/1 [==============================] - 0s 441us/step - loss: 0.2155 - acc: 0.7500
    Epoch 84/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2139 - acc: 0.7500
    Epoch 85/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.2122 - acc: 0.7500
    Epoch 86/300
    1/1 [==============================] - 0s 997us/step - loss: 0.2106 - acc: 0.7500
    Epoch 87/300
    1/1 [==============================] - 0s 996us/step - loss: 0.2090 - acc: 0.7500
    Epoch 88/300
    1/1 [==============================] - 0s 542us/step - loss: 0.2074 - acc: 0.7500
    Epoch 89/300
    1/1 [==============================] - 0s 996us/step - loss: 0.2059 - acc: 0.7500
    Epoch 90/300
    1/1 [==============================] - 0s 3ms/step - loss: 0.2044 - acc: 0.7500
    Epoch 91/300
    1/1 [==============================] - 0s 996us/step - loss: 0.2029 - acc: 0.7500
    Epoch 92/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2015 - acc: 0.7500
    Epoch 93/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.2000 - acc: 0.7500
    Epoch 94/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1986 - acc: 0.7500
    Epoch 95/300
    1/1 [==============================] - 0s 546us/step - loss: 0.1973 - acc: 0.7500
    Epoch 96/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1959 - acc: 0.7500
    Epoch 97/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1946 - acc: 0.7500
    Epoch 98/300
    1/1 [==============================] - 0s 1000us/step - loss: 0.1932 - acc: 0.7500
    Epoch 99/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1919 - acc: 0.7500
    Epoch 100/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1907 - acc: 0.7500
    Epoch 101/300
    1/1 [==============================] - 0s 0s/step - loss: 0.1894 - acc: 0.7500
    Epoch 102/300
    1/1 [==============================] - 0s 998us/step - loss: 0.1881 - acc: 0.7500
    Epoch 103/300
    1/1 [==============================] - 0s 415us/step - loss: 0.1869 - acc: 0.7500
    Epoch 104/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1857 - acc: 0.7500
    Epoch 105/300
    1/1 [==============================] - 0s 990us/step - loss: 0.1845 - acc: 0.7500
    Epoch 106/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1833 - acc: 0.7500
    Epoch 107/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1822 - acc: 0.7500
    Epoch 108/300
    1/1 [==============================] - 0s 982us/step - loss: 0.1810 - acc: 0.7500
    Epoch 109/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1799 - acc: 0.7500
    Epoch 110/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1787 - acc: 0.7500
    Epoch 111/300
    1/1 [==============================] - 0s 994us/step - loss: 0.1776 - acc: 0.7500
    Epoch 112/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1765 - acc: 0.7500
    Epoch 113/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1755 - acc: 0.7500
    Epoch 114/300
    1/1 [==============================] - 0s 921us/step - loss: 0.1744 - acc: 0.7500
    Epoch 115/300
    1/1 [==============================] - 0s 984us/step - loss: 0.1733 - acc: 0.7500
    Epoch 116/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1723 - acc: 0.7500
    Epoch 117/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1712 - acc: 0.7500
    Epoch 118/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1702 - acc: 0.7500
    Epoch 119/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1692 - acc: 0.7500
    Epoch 120/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1682 - acc: 0.7500
    Epoch 121/300
    1/1 [==============================] - 0s 998us/step - loss: 0.1672 - acc: 0.7500
    Epoch 122/300
    1/1 [==============================] - 0s 576us/step - loss: 0.1663 - acc: 0.7500
    Epoch 123/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1653 - acc: 0.7500
    Epoch 124/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1643 - acc: 0.7500
    Epoch 125/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1634 - acc: 0.7500
    Epoch 126/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1625 - acc: 0.7500
    Epoch 127/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1615 - acc: 0.7500
    Epoch 128/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1606 - acc: 0.7500
    Epoch 129/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1597 - acc: 0.7500
    Epoch 130/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1588 - acc: 0.7500
    Epoch 131/300
    1/1 [==============================] - 0s 986us/step - loss: 0.1579 - acc: 0.7500
    Epoch 132/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1570 - acc: 0.7500
    Epoch 133/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1562 - acc: 0.7500
    Epoch 134/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1553 - acc: 0.7500
    Epoch 135/300
    1/1 [==============================] - 0s 401us/step - loss: 0.1545 - acc: 0.7500
    Epoch 136/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1536 - acc: 0.7500
    Epoch 137/300
    1/1 [==============================] - 0s 987us/step - loss: 0.1528 - acc: 0.7500
    Epoch 138/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1520 - acc: 0.7500
    Epoch 139/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1511 - acc: 0.7500
    Epoch 140/300
    1/1 [==============================] - 0s 622us/step - loss: 0.1503 - acc: 0.7500
    Epoch 141/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1495 - acc: 0.7500
    Epoch 142/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1487 - acc: 0.7500
    Epoch 143/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1480 - acc: 0.7500
    Epoch 144/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1472 - acc: 0.7500
    Epoch 145/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1464 - acc: 0.7500
    Epoch 146/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1456 - acc: 0.7500
    Epoch 147/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1449 - acc: 0.7500
    Epoch 148/300
    1/1 [==============================] - 0s 995us/step - loss: 0.1441 - acc: 0.7500
    Epoch 149/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1434 - acc: 0.7500
    Epoch 150/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1427 - acc: 0.7500
    Epoch 151/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1419 - acc: 0.7500
    Epoch 152/300
    1/1 [==============================] - 0s 937us/step - loss: 0.1412 - acc: 0.7500
    Epoch 153/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1405 - acc: 0.7500
    Epoch 154/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1398 - acc: 0.7500
    Epoch 155/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1391 - acc: 0.7500
    Epoch 156/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1384 - acc: 0.7500
    Epoch 157/300
    1/1 [==============================] - 0s 808us/step - loss: 0.1377 - acc: 0.7500
    Epoch 158/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1370 - acc: 0.7500
    Epoch 159/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1364 - acc: 0.7500
    Epoch 160/300
    1/1 [==============================] - 0s 962us/step - loss: 0.1357 - acc: 0.7500
    Epoch 161/300
    1/1 [==============================] - 0s 998us/step - loss: 0.1350 - acc: 0.7500
    Epoch 162/300
    1/1 [==============================] - 0s 946us/step - loss: 0.1344 - acc: 0.7500
    Epoch 163/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1337 - acc: 0.7500
    Epoch 164/300
    1/1 [==============================] - 0s 721us/step - loss: 0.1331 - acc: 0.7500
    Epoch 165/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1325 - acc: 0.7500
    Epoch 166/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1318 - acc: 0.7500
    Epoch 167/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1312 - acc: 0.7500
    Epoch 168/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1306 - acc: 0.7500
    Epoch 169/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1300 - acc: 0.7500
    Epoch 170/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1294 - acc: 0.7500
    Epoch 171/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1288 - acc: 0.7500
    Epoch 172/300
    1/1 [==============================] - 0s 995us/step - loss: 0.1282 - acc: 0.7500
    Epoch 173/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1276 - acc: 0.7500
    Epoch 174/300
    1/1 [==============================] - 0s 994us/step - loss: 0.1270 - acc: 0.7500
    Epoch 175/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1264 - acc: 0.7500
    Epoch 176/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1258 - acc: 0.7500
    Epoch 177/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1253 - acc: 0.7500
    Epoch 178/300
    1/1 [==============================] - 0s 998us/step - loss: 0.1247 - acc: 0.7500
    Epoch 179/300
    1/1 [==============================] - 0s 455us/step - loss: 0.1242 - acc: 0.7500
    Epoch 180/300
    1/1 [==============================] - 0s 927us/step - loss: 0.1236 - acc: 0.7500
    Epoch 181/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1231 - acc: 0.7500
    Epoch 182/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1225 - acc: 0.7500
    Epoch 183/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1220 - acc: 0.7500
    Epoch 184/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1214 - acc: 0.7500
    Epoch 185/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1209 - acc: 0.7500
    Epoch 186/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1204 - acc: 0.7500
    Epoch 187/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1199 - acc: 0.7500
    Epoch 188/300
    1/1 [==============================] - 0s 682us/step - loss: 0.1194 - acc: 0.7500
    Epoch 189/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1189 - acc: 0.7500
    Epoch 190/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1184 - acc: 0.7500
    Epoch 191/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1179 - acc: 0.7500
    Epoch 192/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1174 - acc: 1.0000
    Epoch 193/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1169 - acc: 1.0000
    Epoch 194/300
    1/1 [==============================] - 0s 500us/step - loss: 0.1164 - acc: 1.0000
    Epoch 195/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1159 - acc: 1.0000
    Epoch 196/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1154 - acc: 1.0000
    Epoch 197/300
    1/1 [==============================] - 0s 987us/step - loss: 0.1150 - acc: 1.0000
    Epoch 198/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1145 - acc: 1.0000
    Epoch 199/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1140 - acc: 1.0000
    Epoch 200/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1136 - acc: 1.0000
    Epoch 201/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1131 - acc: 1.0000
    Epoch 202/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1127 - acc: 1.0000
    Epoch 203/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1122 - acc: 1.0000
    Epoch 204/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1118 - acc: 1.0000
    Epoch 205/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1114 - acc: 1.0000
    Epoch 206/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1109 - acc: 1.0000
    Epoch 207/300
    1/1 [==============================] - 0s 900us/step - loss: 0.1105 - acc: 1.0000
    Epoch 208/300
    1/1 [==============================] - 0s 839us/step - loss: 0.1101 - acc: 1.0000
    Epoch 209/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1096 - acc: 1.0000
    Epoch 210/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1092 - acc: 1.0000
    Epoch 211/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1088 - acc: 1.0000
    Epoch 212/300
    1/1 [==============================] - 0s 456us/step - loss: 0.1084 - acc: 1.0000
    Epoch 213/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1080 - acc: 1.0000
    Epoch 214/300
    1/1 [==============================] - 0s 988us/step - loss: 0.1076 - acc: 1.0000
    Epoch 215/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1072 - acc: 1.0000
    Epoch 216/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1068 - acc: 1.0000
    Epoch 217/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1064 - acc: 1.0000
    Epoch 218/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1060 - acc: 1.0000
    Epoch 219/300
    1/1 [==============================] - 0s 965us/step - loss: 0.1056 - acc: 1.0000
    Epoch 220/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1053 - acc: 1.0000
    Epoch 221/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1049 - acc: 1.0000
    Epoch 222/300
    1/1 [==============================] - 0s 995us/step - loss: 0.1045 - acc: 1.0000
    Epoch 223/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1041 - acc: 1.0000
    Epoch 224/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1038 - acc: 1.0000
    Epoch 225/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1034 - acc: 1.0000
    Epoch 226/300
    1/1 [==============================] - 0s 998us/step - loss: 0.1030 - acc: 1.0000
    Epoch 227/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1027 - acc: 1.0000
    Epoch 228/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1023 - acc: 1.0000
    Epoch 229/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1020 - acc: 1.0000
    Epoch 230/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.1016 - acc: 1.0000
    Epoch 231/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.1013 - acc: 1.0000
    Epoch 232/300
    1/1 [==============================] - 0s 997us/step - loss: 0.1009 - acc: 1.0000
    Epoch 233/300
    1/1 [==============================] - 0s 986us/step - loss: 0.1006 - acc: 1.0000
    Epoch 234/300
    1/1 [==============================] - 0s 996us/step - loss: 0.1003 - acc: 1.0000
    Epoch 235/300
    1/1 [==============================] - 0s 996us/step - loss: 0.0999 - acc: 1.0000
    Epoch 236/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.0996 - acc: 1.0000
    Epoch 237/300
    1/1 [==============================] - 0s 998us/step - loss: 0.0993 - acc: 1.0000
    Epoch 238/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0990 - acc: 1.0000
    Epoch 239/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0986 - acc: 1.0000
    Epoch 240/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0983 - acc: 1.0000
    Epoch 241/300
    1/1 [==============================] - 0s 995us/step - loss: 0.0980 - acc: 1.0000
    Epoch 242/300
    1/1 [==============================] - 0s 984us/step - loss: 0.0977 - acc: 1.0000
    Epoch 243/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0974 - acc: 1.0000
    Epoch 244/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0971 - acc: 1.0000
    Epoch 245/300
    1/1 [==============================] - 0s 995us/step - loss: 0.0968 - acc: 1.0000
    Epoch 246/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0965 - acc: 1.0000
    Epoch 247/300
    1/1 [==============================] - 0s 995us/step - loss: 0.0962 - acc: 1.0000
    Epoch 248/300
    1/1 [==============================] - 0s 963us/step - loss: 0.0959 - acc: 1.0000
    Epoch 249/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.0956 - acc: 1.0000
    Epoch 250/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.0953 - acc: 1.0000
    Epoch 251/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0950 - acc: 1.0000
    Epoch 252/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0947 - acc: 1.0000
    Epoch 253/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0945 - acc: 1.0000
    Epoch 254/300
    1/1 [==============================] - 0s 998us/step - loss: 0.0942 - acc: 1.0000
    Epoch 255/300
    1/1 [==============================] - 0s 532us/step - loss: 0.0939 - acc: 1.0000
    Epoch 256/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0936 - acc: 1.0000
    Epoch 257/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0934 - acc: 1.0000
    Epoch 258/300
    1/1 [==============================] - 0s 698us/step - loss: 0.0931 - acc: 1.0000
    Epoch 259/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0928 - acc: 1.0000
    Epoch 260/300
    1/1 [==============================] - 0s 981us/step - loss: 0.0926 - acc: 1.0000
    Epoch 261/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0923 - acc: 1.0000
    Epoch 262/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.0920 - acc: 1.0000
    Epoch 263/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0918 - acc: 1.0000
    Epoch 264/300
    1/1 [==============================] - 0s 697us/step - loss: 0.0915 - acc: 1.0000
    Epoch 265/300
    1/1 [==============================] - 0s 474us/step - loss: 0.0913 - acc: 1.0000
    Epoch 266/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0910 - acc: 1.0000
    Epoch 267/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0908 - acc: 1.0000
    Epoch 268/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0905 - acc: 1.0000
    Epoch 269/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0903 - acc: 1.0000
    Epoch 270/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0900 - acc: 1.0000
    Epoch 271/300
    1/1 [==============================] - 0s 996us/step - loss: 0.0898 - acc: 1.0000
    Epoch 272/300
    1/1 [==============================] - 0s 996us/step - loss: 0.0896 - acc: 1.0000
    Epoch 273/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0893 - acc: 1.0000
    Epoch 274/300
    1/1 [==============================] - 0s 920us/step - loss: 0.0891 - acc: 1.0000
    Epoch 275/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.0889 - acc: 1.0000
    Epoch 276/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.0886 - acc: 1.0000
    Epoch 277/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0884 - acc: 1.0000
    Epoch 278/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0882 - acc: 1.0000
    Epoch 279/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.0880 - acc: 1.0000
    Epoch 280/300
    1/1 [==============================] - 0s 998us/step - loss: 0.0878 - acc: 1.0000
    Epoch 281/300
    1/1 [==============================] - 0s 581us/step - loss: 0.0875 - acc: 1.0000
    Epoch 282/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.0873 - acc: 1.0000
    Epoch 283/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0871 - acc: 1.0000
    Epoch 284/300
    1/1 [==============================] - 0s 982us/step - loss: 0.0869 - acc: 1.0000
    Epoch 285/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0867 - acc: 1.0000
    Epoch 286/300
    1/1 [==============================] - 0s 998us/step - loss: 0.0865 - acc: 1.0000
    Epoch 287/300
    1/1 [==============================] - 0s 0s/step - loss: 0.0863 - acc: 1.0000
    Epoch 288/300
    1/1 [==============================] - 0s 996us/step - loss: 0.0861 - acc: 1.0000
    Epoch 289/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0859 - acc: 1.0000
    Epoch 290/300
    1/1 [==============================] - 0s 813us/step - loss: 0.0857 - acc: 1.0000
    Epoch 291/300
    1/1 [==============================] - 0s 2ms/step - loss: 0.0855 - acc: 1.0000
    Epoch 292/300
    1/1 [==============================] - 0s 998us/step - loss: 0.0853 - acc: 1.0000
    Epoch 293/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0851 - acc: 1.0000
    Epoch 294/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0849 - acc: 1.0000
    Epoch 295/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0847 - acc: 1.0000
    Epoch 296/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0845 - acc: 1.0000
    Epoch 297/300
    1/1 [==============================] - 0s 1ms/step - loss: 0.0843 - acc: 1.0000
    Epoch 298/300
    1/1 [==============================] - 0s 997us/step - loss: 0.0841 - acc: 1.0000
    Epoch 299/300
    1/1 [==============================] - 0s 998us/step - loss: 0.0839 - acc: 1.0000
    Epoch 300/300
    1/1 [==============================] - 0s 987us/step - loss: 0.0837 - acc: 1.0000
    




    <keras.callbacks.History at 0x2772805a670>




```python

```


```python
# 입력데이터를 모델에 넣어서 어떤값으로 예상하는지 확인하기
result = model.predict(x)
print(result)     
```

    [[0.39471388]
     [0.93451077]
     [0.6108011 ]
     [1.150598  ]]
    


```python

```


```python
result = model.predict(x)
print(result.round())    
```

    [[0.]
     [1.]
     [1.]
     [1.]]
    


```python

```


```python
print( list ( model.get_weights() ) )           # 최종 가중치 출력
```

    [array([[0.5397969 ],
           [0.21608725]], dtype=float32), array([0.39471388], dtype=float32)]
    


```python

```


```python
print( model.evaluate(x,y) )             # 오차와 정확도 출력
```

    1/1 [==============================] - 0s 43ms/step - loss: 0.0836 - acc: 1.0000
    [0.08356085419654846, 1.0]
    


```python

```


```python

```
