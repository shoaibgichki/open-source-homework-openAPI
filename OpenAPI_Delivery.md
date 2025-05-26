# OpenAPI Tasarımı Ödevi Teslim Raporu

## 👤 Öğrenci Bilgileri
- **Ad Soyad**: Shoaib Khalil Gichki
- **Öğrenci Numarası**: 170421925

---

## 📂 OpenAPI YAML Dosyası

- **openapi.yaml** dosyasını projenizin GitHub reposuna yükledim.  
- Swagger Editor (https://editor.swagger.io) üzerinde dosyamı test ettim ve doğruluğunu kontrol ettim.

### 🔗 GitHub Repo Linki  
https://github.com/shoaibgichki/open-source-homework-openAPI
---

## 📝 API Açıklaması

Bu proje için aşağıdaki varlıklar (entities) tanımlanmıştır:

- **books**: Kitap bilgilerini tutan varlık (id, title, author, isbn, publisher, pageCount, stock)
- **students**: Öğrenci bilgilerini tutan varlık (id, name, studentNumber, email, isActive)
- **loans**: Kitap ödünç alma işlemleri (id, studentId, bookId, loanDate, returnDate, status)

CRUD işlemleri aşağıdaki endpoint’lerle sağlanmaktadır:

- `/books` endpointinde GET, POST, PUT, DELETE işlemleri  
- `/students` endpointinde GET, POST, PUT, DELETE işlemleri  
- `/loans` endpointinde GET, POST, PATCH işlemleri (kitap iade için özel PATCH)

Dosyada `components/schemas` bölümünde tüm veri modelleri (books, students, loans) detaylı şekilde tanımlanmıştır.  
`parameters` kısmında hem path (`{id}`), hem query (sayfalama için `page` ve `size`) parametreleri kullanılmıştır.  
`responses` bölümünde her endpoint için 200, 201, 400, 404 ve 500 hata kodları örneklerle belirtilmiştir.

Sayfalama, **GET /books** endpointinde `page` ve `size` query parametreleriyle uygulanmıştır.  
Hata durumları için uygun HTTP durum kodları ve açıklayıcı mesajlar eklenmiştir.

---

## 🧪 Test Notları (Opsiyonel)

Swagger Editor’da test ettiğim örnek istek/yanıtlar:

- **GET /books** çağrısı başarılı olduğunda kitap listesi ve sayfalama bilgisi döner. Örnek:  
```json
{
  "totalItems": 50,
  "page": 1,
  "size": 10,
  "items": [
    {
      "id": "123e4567-e89b-12d3-a456-426614174000",
      "title": "Örnek Kitap",
      "author": "Yazar Adı",
      "isbn": "978-3-16-148410-0",
      "publisher": "Yayınevi",
      "pageCount": 300,
      "stock": 5
    }
  ]
}
