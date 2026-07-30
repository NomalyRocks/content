---
order: 4
year: "2026"
code: MDL-04
placeholder: false
stack: [RunPod, ComfyUI, LoRA, Python, Diffusion models]
en:
  name: AI Influencer Models
  summary: >-
    A commissioned character model set: the dataset was collected and cleaned,
    LoRAs were trained across more than one base model, and a separate realism
    pass handles the part that decides whether an image reads as a photograph.
  client: Confidential client
  role: Dataset collection, GPU cluster setup, LoRA and realism model training
  tags: [AI systems, Model training]
  challenge: >-
    An influencer account needs one face to survive hundreds of photographs
    across different light, angles and wardrobe. A general image model gives a
    slightly different person every time, and even when the identity holds the
    render gives itself away — skin too even, texture too clean, the look people
    now recognise on sight. Those are two separate failures and a single prompt
    fixes neither.
  solution: >-
    They were treated as two problems with two models. Identity came from a
    dataset assembled and cleaned for the character, with LoRAs trained on more
    than one base rather than committing to one in advance — which base holds a
    likeness depends on the render setup it ends up in, so the comparison had to
    be run rather than assumed. Realism was trained separately, aimed at skin
    texture, grain and lens behaviour. Training ran on rented GPUs sized per run
    and released afterwards, so the compute cost tracked the training that
    actually happened instead of hardware sitting idle between rounds.
  result: >-
    The model files were delivered to the client, who generates from them
    themselves — the pipeline is theirs, not a service they have to come back
    to. What that means for this page is that the work cannot be inspected here:
    the output belongs to the client and the audience numbers behind it are
    theirs to publish, not ours. What we can state is the deliverable and the
    method.
tr:
  name: AI Influencer Modelleri
  summary: >-
    Sipariş üzerine karakter modeli seti: veri seti toplanıp temizlendi, birden
    fazla base model üzerinde LoRA eğitildi ve bir görselin fotoğraf gibi okunup
    okunmadığına karar veren kısım için ayrı bir realism modeli çalıştırıldı.
  client: İsmi gizli müşteri
  role: Veri seti toplama, GPU cluster kurulumu, LoRA ve realism modeli eğitimi
  tags: [Yapay zekâ sistemleri, Model eğitimi]
  challenge: >-
    Influencer hesabı, tek bir yüzün farklı ışık, açı ve kıyafet altında
    yüzlerce fotoğraf boyunca ayakta kalmasını istiyor. Genel bir görsel modeli
    her seferinde birazcık başka bir insan veriyor; kimlik tutsa bile render
    kendini ele veriyor — cilt fazla düzgün, doku fazla temiz, artık bakar
    bakmaz tanınan o görüntü. Bunlar iki ayrı arıza ve tek bir prompt ikisini de
    çözmüyor.
  solution: >-
    İki ayrı problem, iki ayrı model olarak ele alındı. Kimlik, karakter için
    toplanıp temizlenmiş bir veri setinden geldi; LoRA'lar peşinen tek bir base
    seçilmeden birden fazla base üzerinde eğitildi — hangi base'in benzerliği
    tuttuğu, sonunda hangi render kurulumuna girdiğine bağlı olduğu için
    karşılaştırma varsayılmak yerine koşuldu. Realism ayrı eğitildi; hedefi cilt
    dokusu, grain ve lens davranışıydı. Eğitim, koşu başına boyutlanıp sonrasında
    bırakılan kiralık GPU'larda yürüdü; yani hesaplama maliyeti turlar arasında
    boş bekleyen donanımı değil, gerçekten yapılan eğitimi takip etti.
  result: >-
    Model dosyaları müşteriye teslim edildi; üretimi kendileri yapıyor — hat
    onların, geri dönmek zorunda oldukları bir hizmet değil. Bunun bu sayfa
    açısından anlamı şu: iş burada incelenemiyor. Çıktı müşteriye ait, arkasındaki
    izlenme sayıları da yayınlaması bize değil onlara düşen bir şey. Bizim
    söyleyebileceğimiz, teslimat ve yöntem.
---
