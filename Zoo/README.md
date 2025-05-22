# OOP-Software-Design
객체지향적 소프트웨어 설계 스터디

1. 각 클래스로 생성된 개체는 무슨 역할과 책임을 맡을지 설명한다.
    Animal.cs : animal 개체 Id, name, Species를 담아둠, Equals 메소드를 오버라이딩 하여 객체 간 비교를 할 수 있게 함.
    AnimalCollection.cs : animal 개체 데이터를 뭉탱이로 모아둘 수 있도록 정의한 클래스.
    animal 추가, 삭제를 제공한다.
    Application.cs : 사용자의 입력을 전체적으로 관리하여 animal을 동적으로 생성하여 animalcollection에 추가한다.
    program.cs : Main 함수 싸개
    species.cs : 종을 string으로 처리하지 않고 비교연산과 Find작업을 제공하기 위해 클래스로 구현하여 Equals함수 오버라이딩, operator를 구현해놓았다.
2. 개체의 상태와 동작은 다른 개체와 어떻게 상호작용하는지 설명한다.
    개체간의 구조 : 
    Program.cs에서 Application.cs를 동적으로 생성하여 애플리케이션 시작, 
    Application.cs에서 AnimalCollection을 동적으로 생성후 사용자 입력을 받아 Animal추가를 한다.

    스크립트 내 동작이 다른 개체와 가지는 관계 : 
    Species.cs : operator 연산자를 추가하여 AnimalCollection.cs에서 Find 메소드를 비교 연산자로 구현할 수 있게 함.
    AnimalCollection.cs : AddAnimal 메소드의 반환값을 void로 하지 않고 bool로 하여 Application.cs의 AddAnimals 메소드에서 if연산을 할 수 있도록 함.

3. 개체의 캡슐화가 어떻게 이뤄져 있는지 설명할 수 있어야 한다.
    1. 캡슐화가 적용된 부분이 무엇을 염두에 둔 것인지 생각해 보고 설명한다.
    Animal.cs은 데이터의 저장과 비교연산을 목적으로 작성되었다.
    AnimalCollection.cs은 Animal을 데이터 덩어리로 묶어서 저장하기 위한 것을 목적으로 작성되었다.
    Application.cs는 프로그램의 시작과 끝을 관리하고 사용자의 입력을 받고 판단하기 위함을 목적으로 설계되었다.
    그렇기에 AnimalCollection.cs안에 Find, Add 메소드를 넣어두어 다른 스크립트에서 직접 객체의 필드에 다가가지 않고 메소드를 부를 수 있도록 독립성을 구현하였다.

4. (추가) 이 프로그램 코드는 어떤 기능을 확장하는 데에 염두했는지 생각해 보고 설명한다.
    Application.cs에는 동물 출력과 추가만 구현되어있지만 AnimalCollection.cs에는 삭제 메소드와 Animal의 id, name, species별로 찾는 메소드까지 염두에 두어 설계되어있다.
    
    +혹시나 Animal의 name과 species가 같을 수 있는 경우까지 대비하여 id를 구현해놓은 것인가?

    1. 이 프로그램 코드는 어떤 기능을 확장하지 않도록 염두했는지 생각해 보고 설명한다.
    확장성이 완벽합니다 갓갓갓님