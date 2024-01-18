testControler.tsx

import clientPromise from './index.tsx'
let client;
let db;
let test;

async function initDb(){

    try {
        client = await clientPromise;
        db = await client.db();
        test = db.collecttion('handcraft')
    } catch (error) {
            throw new error('failed to stablishc connection to the tb')
    }
}

index.tsx

import {MongoClient} from 'mongodb'
const URI = process.env.URI
const option =  {}

if (!URI) throw new Error('No URI FOUND');

let client = new MongoClient(URI, option)

let clientPromise;


clientPromise = client.connect();

export default clientPromise;
