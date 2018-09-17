# code-ios-swift

# Danh mục

* [Bài 1: Biến](#Bài-1:-Biến)
* [Bài 2: Các toán tử cơ bản trong Swift](#Bài-2:-Các-toán-tử-cơ-bản-trong-Swift)
* [## Bài 3: Làm việc với String và character trong Swift-phần 1](###-Bài-3:-Làm-việc-với-String-và-character-trong-Swift-phần-1)

## Bài 1: Biến
- 1:
```swift
	let = "constant"
```
*example*
```swift
	let pi =. 2.456
	pi = 346 // error
```
- 2:

```swift
	var = "variable" khai báo biến
```
*example*
```swift
	var abc = "abc", name = "Doan van Du", gmail = = "123@gmail.com"
	var x, y, z : Double
```
- 3: typealias: Bí danh
```swift
 	typealias BigNumber = Double
 	let numberOfAnts: BigNumber = 1000_000_000 // 1000 000 000
 ```
 - 4: nil == null
 ```swift 
 	var numberOfAnts : Int? = 10. // thêm dấu ? để sủ dụng gán nil
 	numberOfAnts = nil
 ```
- 5 : assert (dk, thông báo lỗi nếu đk ko đúng) , precondition (dk, thông báo lỗi nếu đk ko đúng) ==> break or return
```swift
	var numberOfAnts = -10
	assert (numberOfAnts >=0, "đầu vào phải lớn hơn hoặc bằng 0")
	precondition(numberOfAnts >0, "đầu vào phải lớn hơn hoặc bằng 0")
	var x1 = 100 // not run with precondition
```
## Bài 2: Các toán tử cơ bản trong Swift

- 1: Unary operator
```swift
	let iswiftero:Bool = true
	let check = !iswiftero // Unary operator : false
```

- 2: Tuple: Danh sách các biến
```swift
	let (width, height) = (800, 600)
```
- 3: So sánh 2 tuple:
```swift
	(3, "cat") == (3, "cat") // true
```

- 4: for:
```swift
	for index in 1..<5 {
    print("index = \(index)")
   }
```

- 5: if ... else
```swift
	if (5 < 1 || 3 < 2) {
    	print("true !")
	} else {
    	print("false")
	}
```
- 6: range ...
```swift
  let range = ...7 // tất cả những số nhỏ hơn 7
  range.contains(6) // true
```
- 7: array:

```swift
	let animals = ["cat", "dog", "tiger", "dinosaur"]

	for animal in animals[...2] {
   		 print("animal = \(animal)") // in từng phần tử của mảng
	}

```
## Bài 3: Làm việc với String và character trong Swift-phần 1

- 1: String chứa nhiều dòng và nhiều ký tự đặc biệt

```swift
	let welcome = """
  		This is my tutorial channel.
		"How long have you done this ?". "4 months"
		This is a 3 quotes \"\"\" // thêm 3 dấu nháy
	"""
```

- 2: Khởi tạo và kiểm tra chuỗ rỗng:

```swift

	let aBlankString = String()
	print(aBlankString)
	if (aBlankString.isEmpty == true) {
	    print("It is empty")
	}
```
- 3: Check từng ký tự:

```swift
	for eachCharacter in aMutableString {
	    print("character:           \(eachCharacter)")
	}

	// hoặc

	for index in welcomeString.indices {
    print("eachCharacter = \(welcomeString[index])")
	}
```
- 4: append: công thêm ký tự vào cuối chuỗi

```swift
	let dollarMark: Character = "$"
	aMutableString.append(dollarMark)
	print(aMutableString)
```
- 5: 
```swift
	let width = 500
	let squareArea = "The square area is \(width * width)"
	print(squareArea) // string được tạo ra có tính toán
```
- 6: Sử dụng emoji: 

https://unicode-table.com/en/#000C

```swift
	let ampersandMark = "\u{2602}"
	print(ampersandMark)
```
 - 7: Lấy ký tự trong chuỗi

 ```swift
 	var welcomeString = "Hello World!"
	print(welcomeString[welcomeString.index(welcomeString.startIndex, offsetBy: 4)])
```

- 8: Thêm ký tự vào 1 vị trí nào đó

```swift
	welcomeString.insert("A", at: welcomeString.endIndex)

	// chèn vào tại vị trí trước vị trí cuối cùng

	welcomeString.insert(contentsOf: "AAAA", at: welcomeString.index(before: welcomeString.endIndex))
	print(welcomeString)
```

- 9: So sánh 2 string

```swift
	let myLove1 = "I love you"
	let myLove2 = "I love you"

	if myLove1 == myLove2 {
	    print("Content are equal")
	}
```

- 10 check dk:

```swift
	let stringWithPrefix = "mr Hoang makes this video"
	stringWithPrefix.hasPrefix("mr Hoang1") // chứa ký tự đầu tiên

	let stringWithPostfix = "mr Hoang likes StAr War"
	stringWithPostfix.hasSuffix("Star War") // chứa ký tự cuối cùng
	stringWithPostfix.uppercased().hasSuffix("STAR WAR") // chứa ký tự vị trí bất kỳ ko phân biệt chưa hoa hay thường

```

## Bài 4: Dữ liệu kiểu mảng

```swift
	var someDoubles = [Double]() // khởi tạo mảng rỗng
	someDoubles.append(100.02)  // thêm phần tử
	someDoubles.append(3.2)
	print("number of elements = \(someDoubles.count)") // count: số lượng phần tử

	var tenIntegers = Array(repeating: 5, count: 10) // tạo ra mảng có 10 số 5

	var result1 = tenIntegers + tenIntegers  // cộng 2 mảng với nhau


	var smartPhones = ["iphone", "samsum galaxy", "htc one"]
	smartPhones += ["nokia", "blackberry"]  // cộng mảng
	smartPhones.insert("Xaomi", at: 1) //chèn thêm phần tử vào vị trí thứ nhất
	smartPhones.remove(at: 1)  // xoá bỏ phần tử thứ nhất


	for smartPhone in smartPhones {
    print("each smartphone = \(smartPhone)") // duyệt từng phần tử mảng
	}

	for (index, value) in smartPhones.enumerated() {
	    print("index = \(index), value = \(value)") // duyệt từng phần tử và vị trí của mảng
	}

```

## Bài 5: Kiểu dữ liệu tập hợp, kiểu Set

- 1: 

```swift
	var starWarCharacters: Set<String> = ["Anakin Skywalker", "Luke", "Yoda"]

	if(starWarCharacters.isEmpty){ // check empty
	    print("No characters")
	} else {
	    print("There are \(starWarCharacters.count) characters"). // số phần tử
	}
	starWarCharacters.insert("Leia")  // thêm phần tử
	starWarCharacters.remove("Luke")  // xoá phần tử
	print(starWarCharacters)

	if starWarCharacters.contains("Finn") { // kiểm tra có hay ko phần tử
	    print("List contains Finn")
	} else {
	    print("List does not contain Finn")
	}

	for starWarCharacter in starWarCharacters { // duyệt phần tử
	    print("starWarCharacter = \(starWarCharacter)")
	}
```
- 2: Giao, hợp,  hiệu, ... trong tập hợp

```swift
	let set1: Set = [1, 2,  3, 4, 5,  6,  7]
	let set2: Set = [9, 10, 3, 4, 11, 12, 13]

	let resultSet = set1.intersection(set2) // lấy giao giữa 2 mảng
	let resultSet = set1.union(set2)  // hợp giữa 2 phần tử
	let resultSet = set1.subtracting(set2)  // hiệu của 2 tập hợp
	let resultSet = set1.symmetricDifference(set2)  // lấy những phần tử có trong 1 mà ko có trong 2
```
- 3:

```swift
	let fruits:Set = ["🍎","🥝","🍆","🍇","🍒"]
	let fruitAndDrinks:Set = ["🍎","🥝","🍆","🍇","🍒", "🍺","☕️","🍷"]
	let animals: Set = ["🐇","🐊","🐴","🐓"]
	fruitAndDrinks.isSuperset(of: fruits) // kiểm tra có phải là tập hợp cha ko
	fruits.isSubset(of: fruitAndDrinks)  // kiểm tra có phải là tập hợp con ko

	fruits.isDisjoint(with: animals) // khác nhau hoàn toàn
```



