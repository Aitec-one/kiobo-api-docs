# iOS Example





### Model


```swift
struct Customer: Identifiable, Equatable {
    var id: UUID
    var login: String
    var name: String
    var phone: String
    var email: String
    var photo: String?
    var gender: Gender
    var birthDate: Date
    var promoCode: String
    var defaultCardId: UUID
    var activated: Bool
    var notifications: Bool
    var deliveryAddress: DeliveryAddress 
}    
```
