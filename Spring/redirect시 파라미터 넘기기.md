# redirect시 파라미터 넘기기
``` java
	@RequestMapping(value = "/testPage.do")
	public String testPage2() throws Exception {

		redirect.addAttribute("sn", testVO.getSn());
		
		return "redirect:/testPage.do";
	}
```
redirect.addAttribute()를 사용하여 파라미터를 넘긴다.

``` java
	@RequestMapping(value = "/testPage2.do")
	public String testPage(@RequestParam("sn") int sn) throws Exception {

	}
```
@RequestParam를 사용하여 파라미터를 받는다.
