# CNN을 활용한 sentence classification    

## Summary     
문장 수준의 분류 문제에 word vector와 cnn을 도입한 논문    
(성과) NLP에서 word2vec으로 pre-training한 data를 사용해 CNN을 적용하면 간단한 네트워크임에도 문장 분류에서 높은 성능을 낼 수 있다.    

## 아키텍처 및 알고리즘 원리    
1) n(문장 속 단어의 개수)*k(word vector의 dimension) 크기의 문장 embedding Matrix로 만듦    
2) embedding Matrix와 filter 간 => 여러 종류의 단어 개수별 필터들을 가진 합성곱 계층들     
3) filter별 max pooling => output은 sentence embedding vector    
4) dropout 및 fully connected layer + softmax => 클래스 예측 확률 분포      

## 장점         
1) 문장의 지역 정보를 보존함으로써 단어/표현의 등장순서를 학습에 반영    
2) 병렬 처리 가능해 빠르게 학습 가능    

## 단점    
1) 위치가 가깝다고 두 단어의 의미가 비슷한 건 아님. 따라서 순차적으로 정보를 처리하는 rnn이 가지는 장점을 못 갖는다는 문제가 있음    

## Questions    
-단점을 보완해 CNN과 RNN을 결합하면?    
-n-gram 모델과의 비교    
-naïve bayes를 사용한 sentence classification model과의 비교     
