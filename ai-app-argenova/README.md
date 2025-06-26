# AI App Argenova

Bu proje, haftalık çalışma verilerini analiz eden bir AI asistan uygulamasıdır.

## 🏗️ Proje Mimarisi

Proje MVC (Model-View-Controller) mimarisine uygun olarak düzenlenmiştir:

```
ai-app-argenova/
├── config/           # Yapılandırma dosyaları
│   ├── database.js   # MongoDB bağlantısı
│   └── ai.js         # AI servis yapılandırması
├── models/           # Veritabanı modelleri
│   └── Log.js        # Log şeması
├── controllers/      # İş mantığı
│   └── aiController.js # AI işlemleri
├── routes/           # API route'ları
│   └── aiRoutes.js   # AI endpoint'leri
├── middleware/       # Ara yazılımlar
│   ├── errorHandler.js    # Hata yönetimi
│   └── requestLogger.js   # İstek loglama
├── public/           # Statik dosyalar
│   ├── index.html
│   ├── style.css
│   └── script.js
├── server.js         # Ana sunucu dosyası
├── package.json
└── .env.example      # Environment variables örneği
```

## 🚀 Kurulum ve Çalıştırma

1. Bağımlılıkları yükleyin:

```bash
npm install
```

2. Environment variables dosyasını oluşturun:

```bash
cp .env.example .env
```

3. `.env` dosyasını düzenleyin:

```env
# AI Service Configuration
AI_SERVICE_URL=http://165.232.134.134:8000/v1/completions
AI_TEMPERATURE=0.7
AI_MAX_TOKENS=512

# Server Configuration
PORT=3000
NODE_ENV=development

# Database Configuration
MONGODB_URI=mongodb://localhost:27017/ai_logs
```

4. MongoDB'nin çalıştığından emin olun

5. Uygulamayı başlatın:

```bash
# Production
npm start

# Development (nodemon ile)
npm run dev
```

## 📊 API Endpoint'leri

### POST /api/query

AI sorgusu gönderme

```json
{
    "prompt": "Haftalık çalışma verileriniz..."
}
```

### GET /api/history

Geçmiş sorguları getirme

```
GET /api/history?limit=10&page=1
```

## 🔧 Environment Variables

| Variable         | Açıklama                | Varsayılan                                   |
| ---------------- | ----------------------- | -------------------------------------------- |
| `AI_SERVICE_URL` | AI servis URL'si        | `http://165.232.134.134:8000/v1/completions` |
| `AI_TEMPERATURE` | AI yanıt sıcaklığı      | `0.7`                                        |
| `AI_MAX_TOKENS`  | Maksimum token sayısı   | `512`                                        |
| `PORT`           | Sunucu portu            | `3000`                                       |
| `NODE_ENV`       | Çalışma ortamı          | `development`                                |
| `MONGODB_URI`    | MongoDB bağlantı URL'si | `mongodb://localhost:27017/ai_logs`          |

## 🔧 Özellikler

-   ✅ MVC mimarisi
-   ✅ Hata yönetimi
-   ✅ İstek loglama
-   ✅ Pagination desteği
-   ✅ Graceful shutdown
-   ✅ Environment variable desteği
-   ✅ Input validation
-   ✅ Error handling middleware
-   ✅ Modern responsive UI
-   ✅ AI service configuration

## 🛠️ Teknolojiler

-   **Backend**: Node.js, Express.js
-   **Veritabanı**: MongoDB, Mongoose
-   **AI Servisi**: External AI API
-   **Frontend**: HTML, CSS, JavaScript
-   **Environment**: dotenv

## 📝 Geliştirme

Proje modüler yapıda tasarlanmıştır. Yeni özellikler eklemek için:

1. Model oluşturun (`models/`)
2. Controller ekleyin (`controllers/`)
3. Route tanımlayın (`routes/`)
4. Gerekirse middleware ekleyin (`middleware/`)

## 🔒 Güvenlik

-   Environment variables kullanarak hassas bilgileri koruyun
-   Production ortamında güvenli MongoDB URI kullanın
-   AI servis URL'sini environment variable'da saklayın
