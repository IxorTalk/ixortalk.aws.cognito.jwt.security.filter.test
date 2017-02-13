## Introduction

Test support classes for the JWT filter

Provides annotations to mock a JWT user encoded in the token as well as claims inside the JWT token. 

```    
@Test
@WithMockJwtUser(roles = {"OPERATOR"}, mockJwtClaims = {
       @MockJwtClaim(key = "organizationId", value = "1")
})
public void someTest() throws Exception {

   this.mockMvc.perform(post("/some/service/1")
           .contentType(APPLICATION_JSON)
           .content(objectMapper.writeValueAsBytes(payload()))
           .accept(APPLICATION_JSON))
           .andExpect(status().isForbidden());

}
```       

## License

The MIT License (MIT)

Copyright (c) 2016-present IxorTalk CVBA

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
