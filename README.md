## 테스트
'''mermaid

classDiagram
  class UserInterface {
    +SearchHotels()
    +MakeReservation()
    +ViewReservation()
  }
  class HotelDatabase {
    +CheckAvailability()
    +GetRoomInfo()
    +MakeReservation()
  }
  class ReservationEngine {
    +ProcessReservation()
  }
  class PaymentGateway {
    +ProcessPayment()
  }
  class EmailService {
    +SendReservationConfirmation()
  }
  class NotificationService {
    +SendNotifications()
  }

  UserInterface -- HotelDatabase : Uses
  UserInterface -- ReservationEngine : Uses
  UserInterface -- PaymentGateway : Uses
  UserInterface -- EmailService : Uses
  UserInterface -- NotificationService : Uses

  HotelDatabase -- ReservationEngine : Uses
  HotelDatabase -- EmailService : Uses

  ReservationEngine -- PaymentGateway : Uses

  ReservationEngine -- NotificationService : Uses

  EmailService -- NotificationService : Uses

