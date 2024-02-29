Diffrence between str.slice() and str.substring()

The `str.slice()` and `str.substring()` methods in JavaScript are both used to extract a portion of a string. However, they behave differently in certain scenarios, especially when dealing with negative indices and the handling of the `end` parameter.

### `str.slice(start, end)`

- **Parameters**: `start` is the index at which to start extraction, and `end` is the index at which to end extraction.
- **Behavior with Negative Indices**: If `start` is negative, it is treated as `str.length + start`. If `end` is negative, it is treated as `str.length + end`.
- **Behavior with `end` Index**: If `end` is not provided, the slice goes to the end of the string. If `end` is greater than the string's length, it is treated as `str.length`.
- **Example**: `str.slice(5, 10)` will return `"ahmed"`.

### `str.substring(start, end)`

- **Parameters**: Similar to `slice`, `start` is the index at which to start extraction, and `end` is the index at which to end extraction.
- **Behavior with Negative Indices**: If `start` is negative, it is treated as `str.length + start`. If `end` is negative, it is treated as `str.length + end`.
- **Behavior with `end` Index**: If `end` is not provided, the substring goes to the end of the string. If `end` is greater than the string's length, it is treated as `str.length`.
- **Example**: `str.substring(5, 10)` will return `"ahmed"`.

### Key Differences

- **Handling of `end` Parameter**: Both methods treat the `end` parameter similarly, but the key difference lies in how they handle the `end` parameter when it is not provided. In both cases, if `end` is not provided, the method extracts to the end of the string. However, the behavior of these methods when `end` is greater than the string's length is slightly different. For `slice`, if `end` is greater than the string's length, it is treated as `str.length`, effectively extracting to the end of the string. For `substring`, if `end` is greater than the string's length, it is treated as `str.length`, but the method will still extract up to the original string's length, not the extended `end` value.

In summary, while `str.slice()` and `str.substring()` are very similar and can often be used interchangeably, the slight difference in handling the `end` parameter when it is greater than the string's length is a key distinction. However, in most practical scenarios, especially when the `end` parameter is not provided or is within the string's length, the two methods behave identically.