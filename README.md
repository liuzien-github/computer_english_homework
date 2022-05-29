## readme

#### readme

https://www.bilibili.com

[test](./TEST.md)

[picture](./picture.jpg)

https://static.nowcoder.com/images/logo_87_87.png

```java
@Controller
public class HomeController {
    @Autowired
    private DiscussPostService discussPostService;

    @RequestMapping(value = "", method = RequestMethod.GET)
    public String getIndexPage() {
        return "redirect:/index/1";
    }

    @RequestMapping(value = "/index/{pageNum}", method = RequestMethod.GET)
    public String getIndexPage(Model model, @PathVariable("pageNum") Integer pageNum) {
        QueryWrapper<DiscussPost> queryWrapper = new QueryWrapper<>();
        queryWrapper.orderByDesc("create_time");
        PageInfo<DiscussPost> pageInfo = discussPostService.
            selectDiscussPostsByPage(pageNum, 10, queryWrapper);
        model.addAttribute("pageInfo", pageInfo);
        model.addAttribute("path", "/index");
        return "index";
    }

    @RequestMapping(value = "/error", method = RequestMethod.GET)
    public String getErrorPage() {
        return "error/500";
    }
}
```

> this is a block quote.

- read
- green
- blue

1. one
2. two
3. three

| 表头 | 表头 |
| ---- | ---- |
| 1    | 3    |
| 2    | 4    |

**text**

*text*

~~删除线~~

---



