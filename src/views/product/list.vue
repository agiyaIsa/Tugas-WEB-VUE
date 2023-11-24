<template>
    <div>
        <Menu/>
        <div class="container">
            <h1 class="m0">Product</h1>
            <div class="row">
                <div class="col">
                    <p class="mt5 mb20 tc-green">Manage your product details</p>
                </div>
                <div class="col flex">
                    <router-link to="/add-product">
                        <button class="bt-green">+ Add</button>
                    </router-link>
                </div>
            </div>
            <div class="row bg-blue mt10 p10">
                <div class="col">
                    <input
                        class="search-field"
                        type="text"
                        id="deskripsi"
                        placeholder="Tambah deskripsi..."
                    />
                </div>
                <div class="col flex">
                    <button class="bt-blue">Filter</button>
                </div>
            </div>
            <div class="mt50">
                <table>
                    <thead>
                        <tr>
                            <th>PRODUCT CODE</th>
                            <th>PRODUCT NAME</th>
                            <th>PRICE</th>
                            <th>STATUS</th>
                            <th>PRODUCT CATEGORY</th>
                            <th>UNIT</th>
                            <th>PRODUCT STATUS</th>
                            <th>PRODUCT IMAGE</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="item of list_product" :key="item.id">
                            <td class="center">{{ item.productcode }}</td>
                            <td class="center">{{ item.productname }}</td>
                            <td class="center">{{ item.price }}</td>
                            <td class="center">
                                <div v-if="item.status === 'Publish'">
                                    <label class="label-green">Publish</label>
                                </div>
                            </td>
                            <td class="center">{{ item.productcategory }}</td>
                            <td class="center">{{ item.unit }}</td>
                            <td class="center">
                                <div v-if="item.productstatus === 'Availability'">
                                    <label class="label-green">Availability</label>
                                </div>
                                <div v-else>
                                    <label class="label-red">Unavailability</label>
                                </div>
                            </td>
                            <td><img :src="item.img" width="100" alt=""></td>
                            <td class="center">
                                <div class="mt8`">
                                    <router-link to="/edit-product">
                                        <img src="../../assets/icons/edit.svg">
                                    </router-link>
                                </div>
                                <div class="mt5">
                                    <router-link to="/detail-product">
                                        <img src="../../assets/icons/detail.svg">
                                    </router-link>
                                </div>
                                <div class="mt5">
                                    <img src="../../assets/icons/delete.svg">
                                </div>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
import Menu from "../../components/menu.vue"

export default {
	name: 'list-product',
	components: {
		Menu
	},
    data(){
        return {
            list_product: [
                {
                    id: "1",
                    productcode: "Vkwdwn289",
                    productname: "Samsung S21 Ultra",
                    price: "Rp 5.750.000",
                    status: "Publish",
                    productcategory: "Electronic",
                    unit: "20",
                    productstatus: "Availability",
                    role: 1,
                    img: "https://phonesdata.com/files/models/Samsung-Galaxy-S21-Ultra-5G-821.jpg"
                },
                {
                    id: "2",
                    productcode: "ijofj090",
                    productname: "Iphone 15 Pro",
                    price: "Rp 30.000.000",
                    status: "Publish",
                    productcategory: "Electronic",
                    unit: "20",
                    productstatus: "Unavailability",
                    role: 2,
                    img: "https://www.notebookcheck.net/fileadmin/Notebooks/News/_nc3/iphone_15_pro_no_notch.jpg"
                },
                {
                    id: "3",
                    productcode: "kjmpep90",
                    productname: "Iphone 14 Pro",
                    price: "Rp 17.500.000",
                    status: "Publish",
                    productcategory: "Electronic",
                    unit: "20",
                    productstatus: "Availability",
                    role: 3,
                    img: "https://www.macblog.sk/wp-content/uploads/2022/09/Apple-iPhone-14-Pro-iPhone-14-Pro-Max-deep-purple-220907-scaled.jpg"
                }
                
            ]
        }
    }
}
</script>