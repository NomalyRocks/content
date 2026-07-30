---
order: 3
year: "2026"
code: IMG-03
placeholder: false
stack: [Next.js, TypeScript, React Flow, Zustand, ComfyUI, Flux.2, Qwen-Image-Edit, OpenRouter]
en:
  name: Safelight
  summary: >-
    A node canvas for composite photography: references for the person, the
    pose, the setting and the clothing are wired into a generator, and the
    render goes out either to a hosted model or to your own GPU.
  client: Confidential client, now an in-house product
  role: Product definition, architecture, full-stack and ComfyUI pipeline
  tags: [AI systems, Image pipeline]
  challenge: >-
    A prompt box cannot say "take the pose from this photo, the room from that
    one, and nobody's face but hers". Working that way means editing a ComfyUI
    graph by hand for every extra reference, and the workflow templates people
    start from have exactly two reference slots wired into them.
  solution: >-
    Every reference becomes a typed node on a canvas — person, pose,
    environment, clothing, style, object — and each type carries two
    instructions: how the image is announced inside the prompt, and how a vision
    model should describe it in words with identity, clothing and background
    stripped out. That second path is what stops a pose reference from dragging
    its own background into the frame. The same graph renders through a hosted
    model or through self-hosted ComfyUI, where the template's fixed pair of
    reference branches is rebuilt in code for however many references the node
    actually carries.
  result: >-
    Seven image models sit behind one canvas — four hosted, three on our own GPU
    — and each render is priced individually, so a shoot's spend is a number
    rather than a monthly surprise. With no API key and no GPU the application
    still runs end to end on generated placeholders, which is what makes it
    demonstrable before anyone spends anything. It is a single-operator tool
    rather than a product with accounts: no authentication, no multi-tenancy,
    and it expects to sit beside the machine doing the rendering.
tr:
  name: Safelight
  summary: >-
    Kompozit fotoğraf için node tabanlı bir tuval: kişi, poz, mekân ve kıyafet
    referansları üreticiye bağlanıyor, render ya bulut modeline ya da kendi
    GPU'nuza gidiyor.
  client: İsmi gizli müşteri, artık kendi ürünümüz
  role: Ürün tanımı, mimari, full-stack ve ComfyUI hattı
  tags: [Yapay zekâ sistemleri, Görsel hattı]
  challenge: >-
    Bir prompt kutusu "pozu bu fotoğraftan, odayı şundan al, yüz de sadece onun
    olsun" diyemiyor. Bu şekilde çalışmak, her yeni referans için ComfyUI
    grafiğini elle düzenlemek demek; üstelik herkesin başladığı hazır
    şablonlarda tam olarak iki referans yuvası bağlı geliyor.
  solution: >-
    Her referans tuval üzerinde tipli bir node'a dönüştü — kişi, poz, mekân,
    kıyafet, stil, nesne — ve her tip iki talimat taşıyor: görselin prompt
    içinde nasıl tanıtılacağı ve bir görü modelinin onu kimlik, kıyafet ve
    arka plan ayıklanmış halde nasıl yazıya dökeceği. İkinci yol, poz
    referansının kendi arka planını kadraja sürüklemesini engelleyen şey. Aynı
    grafik hem bulut modelinde hem kendi sunucumuzdaki ComfyUI'da render
    ediliyor; orada şablonun sabit iki referans dalı, node'da kaç referans
    varsa o kadarına kod içinde yeniden inşa ediliyor.
  result: >-
    Tek tuvalin arkasında yedi görsel modeli var — dördü bulutta, üçü kendi
    GPU'muzda — ve her render tek tek fiyatlanıyor, yani bir çekimin maliyeti
    ay sonu sürprizi değil bir sayı. API anahtarı ve GPU olmadan da uygulama
    uçtan uca üretilmiş yer tutucularla çalışıyor; kimse tek kuruş harcamadan
    önce gösterilebilir olmasını sağlayan şey bu. Hesap açılan bir ürün değil,
    tek operatörlük bir araç: kimlik doğrulama yok, çok kiracılık yok ve render
    eden makinenin yanında durmayı bekliyor.
---
