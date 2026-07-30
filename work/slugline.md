---
order: 2
year: "2026"
code: AUT-02
placeholder: false
stack: [Python, Typer, asyncio, Next.js, TypeScript, OpenRouter, ComfyUI, FLUX.1 Kontext]
en:
  name: Slugline
  summary: >-
    A storytelling video's subtitle file goes in and a full set of scene
    illustrations comes out — segmented, prompted and rendered in one command,
    with the same character in every frame.
  client: Self-initiated
  role: Product definition, architecture, pipeline and web console
  tags: [Automation, AI systems]
  challenge: >-
    A ten-minute narration carries somewhere over a hundred illustrations, and
    the slow part is not drawing them — it is deciding where the scenes break
    and writing a brief for each one. Image models make that worse rather than
    better: ask for the same character twice and you get two different people,
    so consistency has to be engineered rather than requested.
  solution: >-
    The subtitle file is parsed into cues, a language model tiles them into
    visual beats under a strict JSON schema, and each beat gets its own art
    prompt before the images are rendered in parallel. Identity is handled three
    ways — reference images attached per scene, a canonical written description
    a vision model derives once from the references, or both together — because
    which one holds depends on the model doing the render. A manifest file is
    the source of truth for the whole run, so an interrupted job resumes without
    re-spending on scenes that already finished, and re-analysing a video
    archives the previous version rather than overwriting it. Nine image models
    sit behind one alias resolver, two of them on our own GPU behind a shim that
    speaks the hosted API's contract — moving generation to local hardware is a
    base URL, not a code change.
  result: >-
    The pipeline runs end to end: one command takes a raw subtitle file to a
    finished illustration set, and the test suite covers it offline with no key
    and no spend. What stopped it was the arithmetic. Hosted image models cost
    four to eight cents a picture, a ten-minute video wants a hundred to a
    hundred and twenty of them, and scenes get re-rendered until they are
    usable — so the bill per video sits above what the output is worth. Renting
    a GPU cuts the per-image cost sharply, but development needs the machine up
    whether or not it is rendering, and the idle hours cost more than the images
    do. So it is shelved rather than abandoned, which the manifest design
    already accounts for: the economics move every time model prices drop or a
    local GPU holds more of the work.
tr:
  name: Slugline
  summary: >-
    Anlatı videosunun altyazı dosyası giriyor, sahne illüstrasyonlarının tamamı
    çıkıyor — tek komutla bölünüyor, promptlanıyor ve render ediliyor; her
    karede aynı karakterle.
  client: Kendi girişimimiz
  role: Ürün tanımı, mimari, üretim hattı ve web konsolu
  tags: [Otomasyon, Yapay zekâ sistemleri]
  challenge: >-
    On dakikalık bir anlatı yüzü aşkın illüstrasyon taşıyor ve yavaş kısım çizim
    değil; sahnelerin nerede kesileceğine karar verip her biri için brief
    yazmak. Görsel modelleri bu işi kolaylaştırmak yerine zorlaştırıyor: aynı
    karakteri iki kez isteyin, iki farklı insan gelsin. Yani tutarlılık
    istenerek değil, mühendislikle sağlanmak zorunda.
  solution: >-
    Altyazı dosyası cue'lara ayrılıyor, bir dil modeli bunları katı bir JSON
    şeması altında görsel bölümlere dağıtıyor, her bölüm kendi sanat promptunu
    alıyor ve görseller paralel render ediliyor. Kimlik üç yoldan korunuyor —
    sahne başına iliştirilen referans görseller, bir görü modelinin
    referanslardan bir kez çıkardığı kanonik yazılı tarif ya da ikisi birden —
    çünkü hangisinin tuttuğu render eden modele göre değişiyor. Tüm koşunun
    doğruluk kaynağı bir manifest dosyası: yarıda kalan iş, biten sahneler için
    yeniden para harcamadan devam ediyor; video yeniden analiz edildiğinde
    önceki sürüm üzerine yazılmak yerine arşivleniyor. Tek bir takma-ad
    çözücünün arkasında dokuz görsel modeli var; ikisi kendi GPU'muzda, bulut
    API'sinin sözleşmesini konuşan bir ara katmanın ardında — üretimi yerel
    donanıma taşımak kod değişikliği değil, bir base URL.
  result: >-
    Hat uçtan uca çalışıyor: tek komut ham altyazı dosyasını bitmiş bir
    illüstrasyon setine götürüyor, test paketi de bunu anahtarsız ve harcamasız,
    çevrimdışı kapsıyor. Durduran şey aritmetik oldu. Bulut görsel modelleri
    görsel başına dört ila sekiz sent, on dakikalık bir video bunlardan yüz ile
    yüz yirmi arası istiyor ve sahneler kullanılabilir hale gelene kadar
    yeniden render ediliyor — yani video başına fatura, çıktının değerinin
    üstüne oturuyor. GPU kiralamak görsel başı maliyeti ciddi biçimde
    düşürüyor, ama geliştirme render edilsin edilmesin makinenin açık kalmasını
    istiyor ve boşta geçen saatler görsellerin kendisinden pahalıya geliyor. Bu
    yüzden bırakılmadı, rafa kaldırıldı — manifest tasarımının zaten hesaba
    kattığı bir durum: model fiyatları her düştüğünde ya da yerel GPU işin daha
    fazlasını taşıdığında denklem yeniden oynuyor.
---
