# byte_buffer
... still in progress ...

C implementation of Java ByteBuffer

Aligns to most methods in Java ByteBuffer

Except:
- `duplication()` and `slice()` were intentionally left out as they would cause a dependency issue during `bb_destroy()`
- `allocate()` is replaced by `bb_create()` to emphasize the need for `bb_destroy()`
- `hasArray`, `allocateDirect`, `isDirect` are not implemented as they are Java specific for native allocation
- get/put for Char is not implemented as there is no equivalent of Java Char in C
- get/put for Float and Double are not implemented as their byte-sizes are uncertain on C


| `ByteBuffer` | `byte_buffer` |
|---|---|
|  | `byte_buffer_t *bb_create(size_t max);` |
|  | `void bb_destroy(byte_buffer_t *bb);` |
| `static ByteBuffer allocate(int capacity)` | n/a |
| `static ByteBuffer allocateDirect(int capacity)` | n/a |
| `byte[] array()` | `char *bb_array(byte_buffer_t *bb);` |
| `int arrayOffset()` | `size_t bb_arrayOffset(byte_buffer_t *bb)` |
| `abstract CharBuffer asCharBuffer()` | n/a |
| `abstract DoubleBuffer asDoubleBuffer()` | n/a |
| `abstract FloatBuffer asFloatBuffer()` | n/a |
| `abstract IntBuffer asIntBuffer()` | n/a |
| `abstract LongBuffer asLongBuffer()` | n/a |
| `abstract ByteBuffer asReadOnlyBuffer()` | n/a |
| `abstract ShortBuffer asShortBuffer()` | n/a |
| `abstract ByteBuffer compact()` | `byte_buffer_t compact(byte_buffer_t *bb);` |
| `int compareTo(ByteBuffer that)` | `int bb_compareTo(byte_buffer_t *bb, byte_buffer_t *that);` |
| `abstract ByteBuffer duplicate()` | n/a |
| `boolean equals(Object ob)` | `int bb_equals(byte_buffer_t *bb, byte_buffer_t *that);` |
| `abstract byte get()` | `char get(byte_buffer_t *bb);` |
| `ByteBuffer get(byte[] dst)` | n/a |
| `ByteBuffer get(byte[] dst, int offset, int length)` | `bb_get_buffer(byte_buffer_t *bb, char *dst, size_t offset, size_t length);` |
| `abstract byte get(int index)` | `char bb_get_index(byte_buffer_t *bb, size_t index);` |
| `abstract char getChar()` | n/a |
| `abstract char getChar(int index)` | n/a |
| `abstract double getDouble()` | n/a |
| `abstract double getDouble(int index)` | n/a |
| `abstract float getFloat()` | n/a |
| `abstract float getFloat(int index)` | n/a |
| `abstract int getInt()` | `int32_t bb_getInt(byte_buffer_t *bb);` |
| `abstract int getInt(int index)` | `int32_t bb_getInt_index(byte_buffer_t *bb, size_t index);` |
| `abstract long getLong()` | `int64_t bb_getLong(byte_buffer_t *bb);` |
| `abstract long getLong(int index)` | `int64_t bb_getLong_index(byte_buffer_t *bb, size_t index);` |
| `abstract short getShort()` | `int16_t bb_getShort(byte_buffer_t *bb);` |
| `abstract short getShort(int index)` | `int16_t bb_getShort_index(byte_buffer_t *bb, size_t index);` |
| `boolean hasArray()` | n/a |
| `int hashCode()` | n/a |
| `abstract boolean isDirect()` | n/a |
| `ByteOrder order()` | `byte_order_t bb_order(byte_buffer_t *bb);` |
| ByteBuffer order(ByteOrder bo) | void bb_order_set(byte_buffer_t *bb, byte_order_t order);|
| `abstract ByteBuffer put(byte b)` | `void bb_put(byte_buffer_t *bb, char c);` |
| `ByteBuffer put(byte[] src)` | |
| `ByteBuffer put(byte[] src, int offset, int length)` | `void bb_put_buffer(byte_buffer_t *bb, char *src, size_t offset, size_t length);` |
| `ByteBuffer put(ByteBuffer src)` | `void bb_put_bb(byte_buffer_t *bb, byte_buffer_t *src);` |
| `abstract ByteBuffer put(int index, byte b)` | `void bb_put_index(byte_buffer_t *bb, size_t index, char c);` |
| `abstract ByteBuffer putChar(char value)` | n/a |
| `abstract ByteBuffer putChar(int index, char value)` | n/a |
| `abstract ByteBuffer putDouble(double value)` | n/a |
| `abstract ByteBuffer putDouble(int index, double value)` | n/a |
| `abstract ByteBuffer putFloat(float value)` | n/a |
| `abstract ByteBuffer putFloat(int index, float value)` | n/a |
| `abstract ByteBuffer putInt(int value)` | `void bb_putInt(byte_buffer_t *bb, int32_t value);` |
| `abstract ByteBuffer putInt(int index, int value)` | `void bb_putInt_index(byte_buffer_t *bb,  size_t index, int32_t value);` |
| `abstract ByteBuffer putLong(int index, long value)` | `void bb_putLong_index(byte_buffer_t *bb,  size_t index, int64_t value);` |
| `abstract ByteBuffer putLong(long value)` | `void bb_putLong(byte_buffer_t *bb, int64_t value);` |
| `abstract ByteBuffer putShort(int index, short value)` | `void bb_putShort_index(byte_buffer_t *bb,  size_t index, int16_t value);` |
| `abstract ByteBuffer putShort(short value)` | `void bb_putShort(byte_buffer_t *bb, int16_t value);` |
| `abstract ByteBuffer slice()` | n/a |
| `static ByteBuffer wrap(byte[] array)` | n/a (length is required by C) |
| `static ByteBuffer wrap(byte[] array, int offset, int length)` | `byte_buffer_t *bb_wrap(char *src, size_t offset, size_t length);` |
| `int capacity()` | `size_t bb_capacity(byte_buffer_t *bb);` |
| `Buffer clear()` | `void bb_clear(byte_buffer_t *bb);` |
| `Buffer flip()` | `void bb_flip(byte_buffer_t *bb);` |
| `abstract boolean hasArray()` | n/a |
| `boolean hasRemaining()` | `int bb_hasRemaining(byte_buffer_t *bb);` |
| `abstract boolean isDirect()` | n/a |
| `abstract boolean isReadOnly()` | |
| `int limit()` | `size_t bb_limit(byte_buffer_t *bb);` |
| `Buffer limit(int newLimit)` | `void bb_limit_set(byte_buffer_t *bb, size_t pos);` |
| `Buffer mark()` | `void bb_mark(byte_buffer_t *bb);` |
| `int position()` | `size_t bb_position(byte_buffer_t *bb);` |
| `Buffer position(int newPosition)` | `void bb_position_set(byte_buffer_t *bb, size_t pos);` |
| `int remaining()` | `size_t bb_remaining(byte_buffer_t *bb);` |
| `Buffer reset()` | `void bb_reset(byte_buffer_t *bb);` |
| `Buffer rewind()` | `void bb_rewind(byte_buffer_t *bb);` |
