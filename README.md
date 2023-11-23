
## ການເຊື່ອມຕໍ່Payment Gateway ດ້ວຍ ReactJS

ທ່ານສາມາດນຳໃຊ້ ReactJs ໃນການເຊື່ອມຕໍ່ກັບ Lailao Payment Gateway ຂອງພວກເຮົາ ກ່ອນອື່ນຫມົດແມ່ນເຮົາຕ້ອງສ້າງໂຄງການ Reactjs ເຊິ່ງລາຍລະອຽດເພີ່ມຕື່ມສາມາດເບິ່ງໄດ້ທີ https://legacy.reactjs.org/docs/create-a-new-react-app.html


## ສ້າງ React App

ສ້າງ React App ເປັນສະພາບແວດລ້ອມທີ່ສະດວກສະບາຍສໍາລັບການຮຽນຮູ້ React, ແລະເປັນວິທີທີ່ດີທີ່ສຸດເພື່ອເລີ່ມຕົ້ນການສ້າງຄໍາຮ້ອງສະຫມັກຫນ້າດຽວໃຫມ່ໃນ React.

ມັນຕັ້ງຄ່າສະພາບແວດລ້ອມການພັດທະນາຂອງທ່ານເພື່ອໃຫ້ທ່ານສາມາດນໍາໃຊ້ຄຸນສົມບັດ JavaScript ຫລ້າສຸດ, ສະຫນອງປະສົບການນັກພັດທະນາທີ່ດີ, ແລະເພີ່ມປະສິດທິພາບແອັບຯຂອງທ່ານໃນການຜະລິດ. ທ່ານຈະຕ້ອງມີ Node >= 14.0.0 ແລະ npm >= 5.6 ໃນເຄື່ອງຂອງເຈົ້າ. ເພື່ອສ້າງໂຄງການ, ດໍາເນີນການ:

```bash
npx create-react-app tutorial-reactjs
cd tutorial-reactjs
npm start
```


ຕໍ້ໄປເຮົາສາມາດເພີ່ມ Library ຕ່າງໆເຊັ່ນ icon, ການສະແດງຮູບພາບ, ການໃຫ້ດາວ ແລະ tailwind ເພື່ອຊ່ວຍໃນການອອກແບບຫນ້າຕາຂອງເຮົາໃຫ້ສວຍງາມຂຶ້ນ ໂດຍພິມຄຳສັ່ງລຸ່ມນີ້
```bash
npm install react-icons react-image-gallery react-rater tailwindcss @headlessui/react  react-qrcode-logo 
```

ເພື່ອຈຳລອງຫນ້າຕາລາຍລະອຽດສິນຄ້າທ່ານສາມາດໃຊ້ source code ລຸ່ມນີ້ເພື່ອຈຳລອງຂຶ້ນມາ ເຮົາຈະໄດ້ຮູບພາບສິນຄ້າ ແລະ ລາຍລະອຽດສິນຄ້າສະແດງຕົວຢ່າງຕາມດ້ານຂວາ

```JSX
import './App.css';
import { AiOutlineHeart } from "react-icons/ai";
import { BiShoppingBag } from "react-icons/bi";
import ReactImageGallery from "react-image-gallery";
import Rater from "react-rater";
import "react-rater/lib/react-rater.css";

const App = () => {
  const productDetailItem = {
    images: [
      {
        original:
          "https://images.pexels.com/photos/90946/pexels-photo-90946.jpeg?auto=compress&cs=tinysrgb&w=600",
        thumbnail:
          "https://images.pexels.com/photos/90946/pexels-photo-90946.jpeg?auto=compress&cs=tinysrgb&w=600",
      },
      {
        original:
          "https://images.pexels.com/photos/1667088/pexels-photo-1667088.jpeg?auto=compress&cs=tinysrgb&w=600",
        thumbnail:
          "https://images.pexels.com/photos/1667088/pexels-photo-1667088.jpeg?auto=compress&cs=tinysrgb&w=600",
      },
      {
        original:
          "https://images.pexels.com/photos/2697787/pexels-photo-2697787.jpeg?auto=compress&cs=tinysrgb&w=600",
        thumbnail:
          "https://images.pexels.com/photos/2697787/pexels-photo-2697787.jpeg?auto=compress&cs=tinysrgb&w=600",
      },
      {
        original:
          "https://images.pexels.com/photos/3373736/pexels-photo-3373736.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
        thumbnail:
          "https://images.pexels.com/photos/3373736/pexels-photo-3373736.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1",
      },
      {
        original:
          "https://images.pexels.com/photos/3910071/pexels-photo-3910071.jpeg?auto=compress&cs=tinysrgb&w=600",
        thumbnail:
          "https://images.pexels.com/photos/3910071/pexels-photo-3910071.jpeg?auto=compress&cs=tinysrgb&w=600",
      },
    ],
    title: "BIG ITALIAN SOFA",
    reviews: "150",
    availability: true,
    brand: "apex",
    category: "Sofa",
    sku: "BE45VGTRK",
    price: 450,
    previousPrice: 599,
    description:
      "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quidem exercitationem voluptate sint eius ea assumenda provident eos repellendus qui neque! Velit ratione illo maiores voluptates commodi eaque illum, laudantium non!",
    size: ["XS", "S", "M", "L", "XL"],
    color: ["gray", "violet", "red"],
  };
  const plusMinuceButton =
    "flex h-8 w-8 cursor-pointer items-center justify-center border duration-100 hover:bg-neutral-100 focus:ring-2 focus:ring-gray-500 active:ring-2 active:ring-gray-500";
  return (
    <section className="container flex-grow mx-auto max-w-[1200px] border-b py-5 lg:grid lg:grid-cols-2 lg:py-10">
      {/* image gallery */}
      <div className="container mx-auto px-4">
        <ReactImageGallery
          showBullets={false}
          showFullscreenButton={false}
          showPlayButton={false}
          items={productDetailItem.images}
        />

        {/* /image gallery  */}
      </div>
      {/* description  */}

      <div className="mx-auto px-5 lg:px-5">
        <h2 className="pt-3 text-2xl font-bold lg:pt-0">
          {productDetailItem.title}
        </h2>
        <div className="mt-1">
          <div className="flex items-center">
            <Rater
              style={{ fontSize: "20px" }}
              total={5}
              interactive={false}
              rating={3.5}
            />

            <p className="ml-3 text-sm text-gray-400">
              ({productDetailItem.reviews})
            </p>
          </div>
        </div>
        <p className="mt-5 font-bold">
          Availability:{" "}
          {productDetailItem.availability ? (
            <span className="text-green-600">In Stock </span>
          ) : (
            <span className="text-red-600">Expired</span>
          )}
        </p>
        <p className="font-bold">
          Brand: <span className="font-normal">{productDetailItem.brand}</span>
        </p>
        <p className="font-bold">
          Cathegory:{" "}
          <span className="font-normal">{productDetailItem.category}</span>
        </p>
        <p className="font-bold">
          SKU: <span className="font-normal">{productDetailItem.sku}</span>
        </p>
        <p className="mt-4 text-4xl font-bold text-violet-900">
          ${productDetailItem.price}{" "}
          <span className="text-xs text-gray-400 line-through">
            ${productDetailItem.previousPrice}
          </span>
        </p>
        <p className="pt-5 text-sm leading-5 text-gray-500">
          {productDetailItem.description}
        </p>
        <div className="mt-6">
          <p className="pb-2 text-xs text-gray-500">Size</p>
          <div className="flex gap-1">
            {productDetailItem.size.map((x, index) => {
              return (
                <div
                  key={index}
                  className="flex h-8 w-8 cursor-pointer items-center justify-center border duration-100 hover:bg-neutral-100 focus:ring-2 focus:ring-gray-500 active:ring-2 active:ring-gray-500"
                >
                  {x}
                </div>
              );
            })}
          </div>
        </div>
        <div className="mt-6">
          <p className="pb-2 text-xs text-gray-500">Color</p>
          <div className="flex gap-1">
            {productDetailItem.color.map((x, index) => {
              return (
                <div
                  key={index}
                  className={`h-8 w-8 cursor-pointer border border-white bg-${x}-600 focus:ring-2 focus:ring-${x}-500 active:ring-2 active:ring-${x}-500`}
                />
              );
            })}
          </div>
        </div>
        <div className="mt-6">
          <p className="pb-2 text-xs text-gray-500">Quantity</p>
          <div className="flex">
            <button className={`${plusMinuceButton}`}>−</button>
            <div className="flex h-8 w-8 cursor-text items-center justify-center border-t border-b active:ring-gray-500">
              1
            </div>
            <button className={`${plusMinuceButton}`}> +</button>
          </div>
        </div>
        <div className="mt-7 flex flex-row items-center gap-6">
          <button className="flex h-12 w-1/3 items-center justify-center bg-violet-900 text-white duration-100 hover:bg-blue-800">
            <BiShoppingBag className="mx-2" />
            Add to cart
          </button>
          <button className="flex h-12 w-1/3 items-center justify-center bg-amber-400 duration-100 hover:bg-yellow-300">
            <AiOutlineHeart className="mx-2" />
            Wishlist
          </button>
        </div>
      </div>
    </section>
  );
};

export default App;
```