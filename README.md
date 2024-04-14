# Polymorphic Buffer

This module provides interfaces and methods for working with polymorphic buffers in TypeScript. Polymorphic buffers are versatile data structures that works both in `Node.JS` and `browser` environments and can be initialized from various sources, such as strings, byte arrays, or existing buffers.


## Installation

To install the module, you can use npm:

```bash
npm install --save @ts-overflow/buffer
```

or using yarn:

```bash
yarn add @ts-overflow/buffer
```


## Usage

```typescript
import Buffer from '@ts-overflow/buffer';

// Example usage of the interfaces and methods provided by the module
// Instantiate a new PolymorphicBuffer
const buf = Buffer.alloc(10);

// Manipulate the buffer
buf.writeUInt32BE(123, 0);

console.log(buf.toString('hex')); // Output: 0000007b

// More examples can be found in the documentation below.
```


## API Documentation

### **Interface: PolymorphicBufferConstructor**

Methods

**alloc(byteLength: number): PolymorphicBuffer**: Allocates a new PolymorphicBuffer of specified byte length.

**wrap(actual: Uint8Array): PolymorphicBuffer**: Wraps the given Uint8Array in a PolymorphicBuffer instance.

**fromString(str: string, options?: BufferInitOptions): PolymorphicBuffer**: Creates a new PolymorphicBuffer instance from the given string.

**fromByteArray(source: number[]): PolymorphicBuffer**: Creates a new PolymorphicBuffer instance from the given array of bytes.

**fromBinaryTail(binaryTail: string): PolymorphicBuffer**: Creates a new PolymorphicBuffer instance from the given binary tail string.

**concat(buffers: PolymorphicBuffer[], totalLength?: number): PolymorphicBuffer**: Creates a new PolymorphicBuffer instance from the given array of PolymorphicBuffer instances.

**fromNodeBuffer(buffer: Buffer, options?: Omit<BufferInitOptions, 'dontUseNodeBuffer'>): PolymorphicBuffer**: Creates a new PolymorphicBuffer instance from the given Buffer.

**fromUint8Array(buffer: Uint8Array, options?: Omit<BufferInitOptions, 'dontUseNodeBuffer'>): PolymorphicBuffer**: Creates a new PolymorphicBuffer instance from the given Uint8Array.


### **Interface: PolymorphicBuffer**

Properties

**buffer: Uint8Array**: The backing store Uint8Array of this PolymorphicBuffer instance.

**byteLength: number**: The number of bytes in this PolymorphicBuffer.

**length: number**: The number of items in this PolymorphicBuffer.
Methods

**slice(start?: number, end?: number): PolymorphicBuffer**: Creates a new PolymorphicBuffer instance with a section of this PolymorphicBuffer.

**clone(): PolymorphicBuffer**: Copies this PolymorphicBuffer instance into a new PolymorphicBuffer instance.

**set(array: PolymorphicBuffer | Uint8Array | ArrayBuffer | ArrayBufferView, offset?: number): void**: Sets the bytes in this PolymorphicBuffer instance from the given source.

**fill(value: number, offset?: number, end?: number): void**: Sets the given value to all bytes in this PolymorphicBuffer instance.

**readUInt32BE(offset: number): number**: Reads an unsigned 32-bit integer from this PolymorphicBuffer instance at the given offset.

**writeUInt32BE(value: number, offset: number): void**: Writes an unsigned 32-bit integer to this PolymorphicBuffer instance at the given offset.

**readUInt32LE(offset: number): number**: Reads an unsigned 32-bit integer from this PolymorphicBuffer instance at the given offset.

**writeUInt32LE(value: number, offset: number): void**: Writes an unsigned 32-bit integer to this PolymorphicBuffer instance at the given offset.

**readUInt8(offset: number): number**: Reads an unsigned 8-bit integer from this PolymorphicBuffer instance at the given offset.

**writeUInt8(value: number, offset: number): void**: Writes an unsigned 8-bit integer to this PolymorphicBuffer instance at the given offset.

**indexOf(subarray: PolymorphicBuffer | Uint8Array, offset?: number): number**: Returns the index of the first occurrence of the given PolymorphicBuffer instance in this PolymorphicBuffer instance.

**toString(encoding?: BufferEncoding): string**: Returns a string representation of the PolymorphicBuffer instance.


## License

THis module is licensed under the [Affero General Public License v3.0](https://fsf.org/agpl-3.0.html). See the [LICENSE](./LICENSE) file for more information.
