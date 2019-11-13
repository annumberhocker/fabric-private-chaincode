<template>
    <div>
        <AuctionHeader></AuctionHeader>
        <BidderMenu></BidderMenu>
        <TestTransactions></TestTransactions>
    </div>
</template>

<script>
    import AuctionHeader from "../components/AppHeader"
    import BidderMenu from '../components/AppMenu'
    import TestTransactions from '../components/TestTransactions'

    export default {

        name: "Test",
        components: {
            AuctionHeader,
            BidderMenu,
            TestTransactions
        }
    }
</script>
