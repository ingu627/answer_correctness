# answer_correctness

Riiid 정답 예측 모델


`[Riiid Answer Correctness Prediction 링크](https://www.kaggle.com/c/riiid-test-answer-prediction)`


### 변수 설명

1. train.csv

| 변수명                         | 설명                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| row_id                         | index                                                        |
| timestamp                      | 사용자별 강의를 보거나 문제를 푼 시간이 누적되는 값          |
| user_id                        | 사용자 고유 번호                                             |
| content_id                     | lectures의 lecture_id, questions의 question_id와 연결된 외래키 |
| content_type_id                | content_id가 lectures와 연결된 값인지 questions와 연결된 값인지 구분하는 값 (0->문제, 1->강의) |
| task_container_id              | 문제 타입 유형의 갯수 (누적)                                 |
| user_answer                    | 사용자가 선택한 답 (0, 1, 2, 3), -1->강의                    |
| answered_correctly             | 사용자 선택한 답의 정답여부 (1->정답, 0->오답, -1->강의)     |
| prior_question_elapsed_time    | 이전 문제를 푸는데 소요된 시간                               |
| prior_question_had_explanation | 이전 문제/문제세트를 푼 후, 해설지 확인 -> True, 확인하지않음-> False |



2. questions.csv : metadata for the questions posed to users

| 변수명         | 설명                                                    |
| -------------- | ------------------------------------------------------- |
| question_id    | 각각의 문제 번호(train/test에 있는 content_id의 외래키) |
| bundle_id      | 문제/문제 묶음의 번호                                   |
| correct_answer | 문제의 정답                                             |
| part           | 토익 part. 1~7                                          |
| tags           | 비슷한 유형의 문제(들)                                  |



3. lectures.csv : metadata for the lectures watched by users as they progress in their education.

| 변수명     | 설명                                                         |
| ---------- | ------------------------------------------------------------ |
| lecture_id | 각각의 강의번호 (train/test에 있는 content_id의 외래키)      |
| tag        | 강의를 위한 코드 넘버링                                      |
| part       | 토익 part 1~7                                                |
| type_of    | 강의 종류(starter : 2, intention : 7 , solving question : 186, concept : 222) |

