

![](https://blog.kakaocdn.net/dn/dhNPfX/btrua4fXCjn/vERD8MeOdSvfHlOotuemLK/img.png)

## Document
- BSON 타입(JSON의 확장 타입)으로, 일반적인 RDB의 **Data Record** 에 해당되는 개념
- *{Key : Value}* Pari 형태로 구성됨
- Value 에는 또 다른 문서 형태가 올 수 있으며, 배열(Array) 타입도 지원
- Document 의 Field 중, 'id' Field는 기본적으로 해당 문서의 Unique Key 값에 해당되는 필드

```Json
{ 
	 _id: ObjectId("5cdd01b66c9add51440e924f"), 
	 field1: value1, 
	 field2: [value1, value2, value3], 
	 ... 
	 fieldN: { 
		 field1: value1, 
		 field2: value2, 
	 } 
 }
```
 
## Collection
- 일반적인 RDB의 Table에 해당하는 개념
- RDB에서는 모든 Record가 동일한 Attribute를 가져야하지만, Collection에 저장된 각각의 Document들은 모두 다른 종류의 Attribute를 가질 수 있다.
- 여러 Document를 보관하기 위한 저장소
- 여러 Document를 용도별로 Collection에 저장할 수 있다.

## Database
1개 이상의 Collection 을 보관하는 저장소로, 가장 상위 개념