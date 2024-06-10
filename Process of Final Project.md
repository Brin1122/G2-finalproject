### Presentation Date : 6/18
- Role : Presenter🗣️ = 김서현 / Teacher👩‍🏫 = 김나영 / Student👩‍🎓 = 추수현
- 5/21 Discussion : 조별로 배정된 문장들을 해석하는 것을 발표한 후 다같이 스토리에 맞게 순서 배열(나눠주는 것에 앱 사용) / 문장에 한 단어 밑줄 친 후 의미가 비슷한 단어 고르기(객관식, 문법 활동)
- 5/28 Discussion : 활동 1. 본문을 몇문장씩 나눈 후 조별로 배분(앱 사용) -> 각자 해석한 내용을 발표한 후 다같이 스토리에 맞게 순서 배열 / 활동 2. 문장별로 한 단어씩 밑줄 친 후 의미가 비슷한 단어 고르기(객관식 문법 문제-앱 사용)
- 활동 목표 : 조별활동을 함으로써 협동력을 키우고 스스로 해석하고 이야기의 흐름을 파악하는 문해력을 키울 수 있다. 유의어에 관한 문제를 풂으로써 어휘력을 키울 수 있다.
- 다음 시간(6/4) 계획 : 코드 작성, 발표 개요 의논
### 📖Our Story
- passage 1 : In the small mountain village of Echo Ridge, adventure was a part of everyday life. Nestled among towering peaks, the village was said to be protected by the "Guardian of the Glen," a massive eagle that supposedly watched over the villagers from its perch high in the mountains. The legend inspired many adventurous tales among the villagers, especially the children.
Among these children was a bright-eyed eighth grader named Alex. Alex was known for his daring spirit and his love for exploring the rugged landscapes around Echo Ridge. He had a particular fascination with the old maps and tales of hidden treasures that had been lost in the mountains centuries ago.
One day, while exploring the local library, Alex stumbled upon an ancient map tucked inside a forgotten book on village lore. The map hinted at the location of a lost treasure, hidden deep within a cave known as Whispering Hollow. Excited by the prospect of a real adventure, Alex decided to seek out the treasure.
- passage 2 : Knowing the journey would be risky, he enlisted the help of his best friends, Mia and - Sam. Together, they prepared for the expedition, gathering supplies and studying the map extensively. They planned their route, took note of landmarks, and readied themselves for any challenges they might face.
Their journey began at dawn. They trekked through dense forests, crossed rushing streams, and climbed steep cliffs. Along the way, they encountered various wildlife and navigated through tricky terrains, their map guiding them every step of the way.
- passage 3 : After hours of hiking, they finally reached Whispering Hollow. The cave was more magnificent than they had imagined, filled with intricate stalactites and echoes of dripping water. Using their flashlights, they ventured deeper into the cave, guided by the markings on the map.
As they reached the heart of the cave, they discovered an ancient chest hidden behind a fallen boulder. With hearts pounding, they moved the boulder and opened the chest. Inside, instead of gold or jewels, they found a collection of old artifacts: pottery, coins, and a beautifully carved statuette of an eagle — the Guardian of the Glen.
- passage 4 : Realizing the historical significance of their find, they decided to donate the artifacts to the local museum. The village celebrated their discovery, and the children were hailed as heroes. Their adventure brought the community together, sparking a renewed interest in the history and legends of Echo Ridge. Alex, Mia, and Sam became local legends, known not only for their daring but also for their spirit of discovery and respect for heritage. They continued to explore the mountains, each adventure strengthening their friendship and deepening their connection to their village.
The legend of the Guardian of the Glen lived on, not just as a protector but as a symbol of adventure and discovery, inspiring future generations to explore the mysteries of Echo Ridge.
- 6/4 코딩 짜기
### Activity 1️⃣
```
# Gradio 설치 (Colab에서는 처음 한 번만 실행)
%%capture
!pip install gradio

import gradio as gr

# 단어와 뜻, 예제를 저장하는 딕셔너리
dictionary = {
    "nestled": {
        "meaning": "Settled comfortably or cozily.",
        "example": "The cabin was nestled in the valley."
    },
    "towering": {
        "meaning": "Very tall or high.",
        "example": "The towering skyscrapers dominated the city skyline."
    },
    "guardian": {
        "meaning": "Someone or something that protects.",
        "example": "The dog was the guardian of the house."
    },
    "perch": {
        "meaning": "A high or elevated position.",
        "example": "The bird sat on its perch, looking out over the field."
    },
    "supposedly": {
        "meaning": "According to what is generally assumed or believed.",
        "example": "Supposedly, this path leads to the hidden cave."
    },
    "adventurous": {
        "meaning": "Willing to take risks or try out new experiences.",
        "example": "She was feeling adventurous and decided to try skydiving."
    },
    "daring": {
        "meaning": "Willing to take bold risks.",
        "example": "His daring escape from the prison was legendary."
    },
    "fascination": {
        "meaning": "A strong interest or attraction.",
        "example": "Her fascination with ancient history led her to become an archaeologist."
    },
    "lore": {
        "meaning": "Traditional knowledge or stories passed down through generations.",
        "example": "The old man shared the lore of the village with the children."
    },
    "expedition": {
        "meaning": "A journey undertaken for a specific purpose, often exploration.",
        "example": "The expedition to the North Pole was a great success."
    },
    "landmark": {
        "meaning": "An object or structure that serves as a point of reference.",
        "example": "The Eiffel Tower is one of Paris's most famous landmarks."
    },
    "trekked": {
        "meaning": "Made a long and difficult journey, especially on foot.",
        "example": "They trekked through the jungle for three days."
    },
    "dense": {
        "meaning": "Thick and hard to see through.",
        "example": "The dense fog made driving very difficult."
    },
    "navigated": {
        "meaning": "Planned and directed the course of a journey.",
        "example": "The captain skillfully navigated the ship through the storm."
    },
    "tricky": {
        "meaning": "Difficult to deal with or handle.",
        "example": "The tricky puzzle took hours to solve."
    },
    "magnificent": {
        "meaning": "Extremely beautiful or impressive.",
        "example": "The view from the mountain top was magnificent."
    },
    "intricate": {
        "meaning": "Very detailed and complicated.",
        "example": "The intricate design on the vase was handmade."
    },
    "stalactite": {
        "meaning": "An icicle-shaped formation that hangs from the ceiling of a cave.",
        "example": "The cave was filled with stalactites and stalagmites."
    },
    "ventured": {
        "meaning": "Went somewhere that might be dangerous.",
        "example": "They ventured into the dark forest despite the warnings."
    },
    "artifact": {
        "meaning": "An object made by humans, typically of historical interest.",
        "example": "The museum displayed artifacts from ancient Egypt."
    }
}

def lookup_word(word):
    word = word.lower()  # 단어를 소문자로 변환하여 검색
    if word in dictionary:
        meaning = dictionary[word]["meaning"]
        example = dictionary[word]["example"]
        return f"Meaning: {meaning}\nExample: {example}"
    else:
        return "Sorry, that word is not in the dictionary."

# Gradio 인터페이스 설정
iface = gr.Interface(
    fn=lookup_word,  # 호출할 함수
    inputs="text",  # 입력 타입
    outputs="text",  # 출력 타입
    title="Dictionary Lookup",  # UI 제목
    description="Enter an English word to get its meaning and an example sentence."  # UI 설명
)

# Gradio 인터페이스 실행
iface.launch()
```
### Activity 2️⃣
```import random
import ipywidgets as widgets
from IPython.display import display

# 학생 이름 리스트
students = ["Group1", "Group2", "Group3", "Group4"]

# 여러 개의 영어 본문 리스트
texts = [
    """Text 1: In the small mountain village of Echo Ridge, adventure was a part of everyday life. Nestled among towering peaks, the village was said to be protected by the "Guardian of the Glen," a massive eagle that supposedly watched over the villagers from its perch high in the mountains. The legend inspired many adventurous tales among the villagers, especially the children. Among these children was a bright-eyed eighth grader named Alex. Alex was known for his daring spirit and his love for exploring the rugged landscapes around Echo Ridge. He had a particular fascination with the old maps and tales of hidden treasures that had been lost in the mountains centuries ago. One day, while exploring the local library, Alex stumbled upon an ancient map tucked inside a forgotten book on village lore. The map hinted at the location of a lost treasure, hidden deep within a cave known as Whispering Hollow. Excited by the prospect of a real adventure, Alex decided to seek out the treasure.""",
    """Text 2: Knowing the journey would be risky, he enlisted the help of his best friends, Mia and - Sam. Together, they prepared for the expedition, gathering supplies and studying the map extensively. They planned their route, took note of landmarks, and readied themselves for any challenges they might face. Their journey began at dawn. They trekked through dense forests, crossed rushing streams, and climbed steep cliffs. Along the way, they encountered various wildlife and navigated through tricky terrains, their map guiding them every step of the way.""",
    """Text 3: After hours of hiking, they finally reached Whispering Hollow. The cave was more magnificent than they had imagined, filled with intricate stalactites and echoes of dripping water. Using their flashlights, they ventured deeper into the cave, guided by the markings on the map. As they reached the heart of the cave, they discovered an ancient chest hidden behind a fallen boulder. With hearts pounding, they moved the boulder and opened the chest. Inside, instead of gold or jewels, they found a collection of old artifacts: pottery, coins, and a beautifully carved statuette of an eagle — the Guardian of the Glen.""",
    """Text 4: Realizing the historical significance of their find, they decided to donate the artifacts to the local museum. The village celebrated their discovery, and the children were hailed as heroes. Their adventure brought the community together, sparking a renewed interest in the history and legends of Echo Ridge. Alex, Mia, and Sam became local legends, known not only for their daring but also for their spirit of discovery and respect for heritage. They continued to explore the mountains, each adventure strengthening their friendship and deepening their connection to their village. The legend of the Guardian of the Glen lived on, not just as a protector but as a symbol of adventure and discovery, inspiring future generations to explore the mysteries of Echo Ridge."""
]

# 학생별로 할당된 본문을 저장하는 사전
student_texts = {student: None for student in students}

# 버튼 클릭 이벤트 핸들러
def on_button_click(b):
    student = student_name.value.strip()  # 학생 이름을 입력받음
    with output:
        output.clear_output()  # 이전 출력 지우기
        if student not in students:
            print("Invalid name. Please enter a valid student name.")
            return
        if student_texts[student] is None:
            if texts:
                chosen_text = random.choice(texts)
                texts.remove(chosen_text)
                student_texts[student] = chosen_text
                print(f"{chosen_text}")
            else:
                print("No more texts available.\n")
        else:
            print(f"{student}, you have already been assigned a text:\n  - {student_texts[student]}\n")

# 학생 이름 입력 위젯
student_name = widgets.Text(
    value='',
    placeholder='Enter your name',
    description='Name:',
    disabled=False
)

# 배분 버튼 위젯
distribute_button = widgets.Button(description="Distribute Text")

# 출력 위젯
output = widgets.Output()

# 버튼 클릭 이벤트 핸들러 연결
distribute_button.on_click(on_button_click)

# 위젯 표시
display(student_name, distribute_button, output)
```
### Activity 3️⃣
```
